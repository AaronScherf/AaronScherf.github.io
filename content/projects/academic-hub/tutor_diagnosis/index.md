---
title: Tutor Diagnosis & Hint Generator
date: 2026-09-28
type: academic-hub-project
image:
  caption: 'Problem-Set Tutor Diagnosis and Hint Generator architecture with 3-axis grading and adversarial verification'
  image_suggestion: "System diagram of the Problem-Set Tutor Diagnosis and Hint Generator: illustrating the /hint pipeline extracting unsolved homework questions and generating non-spoiler direction sketches with negative constraints; the /draft workflow evaluating attempts against a 3-axis rubric (Correctness, Rigor, Course-Fit) with cognitive gap tags; and the /verify adversarial cross-check with persistent logging to .session_log/<course>.jsonl."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/rag
tags:
  - Python
  - LLM / RAG
  - EdTech
---

An interactive extension to the **[RAG Analysis](/projects/academic-hub/rag_analysis/)** tutoring agent designed specifically for problem sets — extracting fresh homework questions, generating motivating direction sketches without giving away the final derivation, diagnosing student drafts against a 3-axis grading rubric, and tracking cognitive gaps over time in a persistent session log.

<!--more-->

*Figure: Problem-Set Tutor Diagnosis and Hint Generator workflow showing non-spoiler hint extraction, 3-axis draft evaluation, adversarial verification, and persistent session logging.*

Standard LLMs fail at authentic tutoring for a fundamental reason: they have no pedagogical model. Hand ChatGPT or Claude a homework question, and it immediately outputs a full, worked proof or final answer. For a graduate student working through advanced microeconomics or econometrics, that blithely short-circuits the cognitive struggle essential for mastering the material.

The motivation for this tool came from auditing real coursework files in `academic_notes/{econometrics,microecon}/problem_sets/`. That audit surfaced a clear pattern in how human mathematical reasoning actually progresses:
- In microeconomics, `homework_1_solutions_notes.md` preserves annotated stages: `[First Attempt]`, `[Wait, what if...]`, and `[Corrected with proper induction]` — a record of where initial intuition failed before self-correcting.
- In econometrics, `problem_set_1_gemini_solutions.md` deliberately juxtaposes a `[Naive Gemini]` subtly flawed proof next to a `[Correct Gemini]` proof with a "Where the Flaw Lies" section to manufacture contrast cases.

In both courses, capturing, diagnosing, and learning from personal reasoning errors was the highest-value signal available. `tutor_diagnosis.py` builds this loop directly into the `rag_agent.py` interactive REPL across four core capabilities:

### 1. `/hint <file> <question-ref>` — Guidance Without Giving Away the Answer
Before a student has an attempt to grade, they often need a nudge to get unstuck. Rather than requiring manual question copy-pasting, `problem_set_parser.py` cleanly extracts a single problem statement from fresh, unsolved problem-set files (e.g. `homework_3.md Question 1`) using section boundary regexes.

The extracted question retrieves relevant textbook and lecture passages through `retrieve_passages()`. Generation is governed by `_HINT_PROMPT_TEMPLATE`, which enforces strict negative constraints:
> *"Give them a motivating sketch of the right technique or theorem to reach for -- enough to get them unstuck and pointed in the right direction. Do NOT state the final answer, a verdict (e.g. True/False), or a worked derivation. If you find yourself about to write out the conclusion, stop and describe the approach instead."*

**Grounding Validation vs. Ungrounded Fallback**: The agent validates whether retrieved passages actually contain the question's core concepts. If course notes lack the required topic (such as Block Marschak / Luce models in microeconomics), the agent avoids hallucinating a forced citation. Instead, it explicitly alerts the student: *"None of your course materials mention [terms] — falling back to a general hint,"* calling `generate_ungrounded_hint()`. An honest, ungrounded on-topic hint beats a confidently wrong hallucination dressed in real citations.

### 2. `/draft` — Diagnosing Attempts on a 3-Axis Rubric
After receiving a hint or initial explanation, the student types `/draft` and pastes their handwritten or typed attempt (terminated by `/end`). `diagnose_draft()` compares the draft against the reference answer and retrieved course excerpts.

Instead of a generic pass/fail verdict, the model evaluates the attempt across a structured **0–5 rubric**:
- **Correctness (0–5)**: Does the draft reach the right mathematical conclusion through valid reasoning?
- **Rigor (0–5)**: Is each step formally justified rather than asserted? Are edge cases, degenerate conditions (such as ties or vacuous truth), and assumptions explicitly handled as required by the course?
- **Course-Fit (0–5)**: Does the proof adopt the professor's idiosyncratic notation, definitions, and framing from course lecture notes rather than generic textbook phrasing?

The model also outputs a short free-text `gap_tag` (such as `vacuous-case-overlooked` or `fundamental-property-misunderstanding`). Re-running `/draft` after revising preserves the sequence of attempts in the session log naturally, allowing the student to see their progression from initial draft to rigorous proof.

### 3. `/verify` — Independent Adversarial Cross-Check
Grounding an answer in retrieved excerpts does not guarantee a flawless proof — models can still make subtle algebraic slips or misapply conditions. `/verify` re-solves the active question using an independent call to a stronger model (`gemini-3.6-flash`).

Crucially, the verifier is *not* shown the tutor's prior answer or retrieved excerpts, preventing it from rationalizing or echoing earlier mistakes. Both solutions are printed side by side for the student to compare. The system intentionally avoids auto-adjudication, leaving the student as the final judge and avoiding brittle multi-LLM consensus loops.

### 4. `/summarize [unit]` & Persistent Gap Memory
Every REPL action appends a structured `Event` to an append-only JSONL log at `.session_log/<course>.jsonl` (gitignored, private). When reviewing a problem set, `/summarize` aggregates logged events to synthesize a "What we learned" / "What to focus on" retrospective, alongside **computed** (not model-generated) rubric score averages across all draft attempts.

In subsequent study sessions, `answer_question()` loads recent gap tags and proactively injects them into its answer prompt — alerting the student if a new question touches a conceptual blind spot diagnosed in previous problem sets.

### Real-Corpus Validation
The system was validated live against real coursework in the Academic Hub repository:
- **Diagnostic Precision**: A deliberately flawed econometrics attempt asserting "residuals are always positive" was correctly scored 0/5 across all three axes and produced the precise gap tag `fundamental-property-misunderstanding`.
- **Non-Spoiler Nudges**: A live test on `homework_3.md` Question 1 (incomplete preference relations) produced a motivating counterexample sketch exploring broken transitivity chains without stating a verdict or writing out the derivation.
- **Independent Divergence**: `/verify` generated an independent proof that surfaced an intercept-term caveat omitted by the tutor model's initial grounded response, confirming the verifier does not echo prior reasoning.

Part of **Academic Hub**, bridging **[RAG Analysis](/projects/academic-hub/rag_analysis/)**, **[Source Indexer](/projects/academic-hub/source_indexer/)**, and **[Problem Generation](/projects/academic-hub/problem_generation/)** into an end-to-end study system.
