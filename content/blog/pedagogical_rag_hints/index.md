---
title: "Pedagogical RAG: Building an AI Tutor That Nudges Instead of Spoiling the Answer"
summary: "Why raw LLMs ruin homework by blurting out full solutions, how I engineered negative prompt constraints in /hint to provide direction sketches without giving away proofs, how the agent validates grounding vs. ungrounded fallbacks, and how a 3-axis grading rubric evaluates student drafts on rigor and course-fit."
date: 2026-09-29
authors:
  - me
tags:
  - Academic Hub
  - LLM / RAG
  - EdTech
  - Python
image:
  caption: 'Pedagogical AI study tutor architecture: comparing raw LLM homework spoiling against non-spoiler hints, grounding checks, and 3-axis draft evaluation'
  image_suggestion: "Software architecture and UI comparison diagram for a pedagogical AI study tutor: contrasting raw LLM homework spoiling against a pedagogical RAG engine featuring the /hint command with strict negative constraints, key-term grounding verification, and the /draft evaluation workflow scoring attempts across a 3-axis rubric (Correctness, Rigor, Course-Fit) with session logging."
---

If you paste an advanced microeconomics or econometrics problem into ChatGPT or Claude, it will cheerfully output a complete, step-by-step proof in under ten seconds. 

On the surface, this looks like magic. In practice, it is toxic for learning.

<!--more-->

*Figure: Pedagogical AI study tutor architecture: comparing raw LLM homework spoiling against non-spoiler hints, grounding checks, and 3-axis draft evaluation.*

Mastering technical disciplines — mathematics, economic theory, statistics, or quantum physics — does not happen by reading someone else’s finished answer. It happens in the **productive struggle**: the messy, uncomfortable period where you test hypotheses, hit dead ends, construct counterexamples, and gradually build an intuitive mental model. The moment an AI hands you a polished derivation, that cognitive struggle evaporates, leaving behind an illusion of competence that collapses the moment exam day arrives.

Worse still, general-purpose LLMs have no concept of course-specific framing. They pull from the entire internet, defaulting to generic Wikipedia phrasing, different notation conventions, or alternative definitions that conflict with what your professor actually taught.

To solve this, I designed and built the **[Tutor Diagnosis & Hint Generator](/projects/academic-hub/tutor_diagnosis/)** — a specialized pedagogical extension to **Academic Hub** that transforms a retrieval agent from a mindless answer engine into an authentic office-hours coach.

---

### 1. Where Real Learning Lives: The Human Error Trail

The design of this system started with an audit of my own coursework notes in `academic_notes/{econometrics,microecon}/problem_sets/`. Inspecting how I actually solved difficult problem sets revealed a clear pattern:

- In microeconomics, `homework_1_solutions_notes.md` preserved an explicit progression: `[First Attempt]` $\longrightarrow$ `[Wait, what if...]` $\longrightarrow$ `[Corrected with proper induction]`. The breakthroughs came directly from identifying where my initial intuition broke down.
- In econometrics, `problem_set_1_gemini_solutions.md` deliberately placed a `[Naive Gemini]` (subtly flawed) proof right next to a `[Correct Gemini]` proof with a dedicated "Where the Flaw Lies" section to manufacture contrast cases.

In both courses, capturing and diagnosing errors was the single highest-value signal in the study process. A real tutor does not just say "here is the proof"; a real tutor looks at your flawed draft, points out the missing edge case, and asks a probing question.

Here is how I implemented that feedback loop in `agent/rag/tutor_diagnosis.py` across an interactive CLI REPL.

---

### 2. `/hint` — Guidance Without Giving Away the Derivation

Before you have an attempt ready to grade, you often hit a roadblock and need a nudge. But you don't want the answer spoiled.

The `/hint <file> <question-ref>` command allows you to point the tutor at a specific problem in a clean, unsolved assignment (for instance, `homework_3.md Question 1`). The tool's parser (`problem_set_parser.py`) extracts the exact question text automatically without requiring manual copy-pasting.

The question then passes into the retrieval layer (`retrieve_passages()`), searching your indexed course lecture notes and textbooks. But instead of generating an answer, the generation prompt enforces **strict negative boundaries**:

```python
_HINT_PROMPT_TEMPLATE = """A student is about to attempt the question below, using ONLY the excerpts \
from their own course materials given here. Give them a motivating sketch of the right technique or \
theorem to reach for -- enough to get them unstuck and pointed in the right direction.

Do NOT state the final answer, a verdict (e.g. True/False), or a worked derivation. If you find \
yourself about to write out the conclusion, stop and describe the approach instead.

Excerpts:
{excerpts_block}

Question: {question}

Hint:"""
```

In a live test against an unsolved question on incomplete preference relations in microeconomics, the agent suggested constructing a counterexample by examining broken transitivity chains — giving the exact direction needed to make progress without revealing whether the proposition was true or false.

---

### 3. The Grounding Dilemma: When Course Materials Fall Short

A major danger in RAG systems is forced citation: if a user asks about a concept that does not exist in the indexed database, a standard RAG agent will often force retrieved passages to fit, resulting in a confidently hallucinated answer supported by irrelevant citations.

To prevent this, the `/hint` command performs an automated **key-term match audit**:
- It extracts the distinctive conceptual terms from the problem statement (e.g., *"Block Marschak"*, *"Luce choice axiom"*).
- It verifies whether the retrieved course passages actually contain those terms.
- **The Honest Fallback**: If no course materials discuss the topic, the agent refuses to fabricate a grounded citation. Instead, it explicitly alerts the student:
  > *"None of your course materials mention Block Marschak — falling back to a general hint (not sourced from your materials; double-check it against them)."*

It then calls `generate_ungrounded_hint()`, using the model’s internal general knowledge. As an engineering decision, **an honest, ungrounded hint beats a confidently wrong cited hallucination every time.**

---

### 4. `/draft` — Diagnosing Attempts on a 3-Axis Rubric

Once you have written a draft solution, you need diagnostic feedback, not just a red checkmark. 

Typing `/draft` in the REPL lets you paste your handwritten or typed attempt. The diagnosis engine compares your reasoning against a reference answer and the cited excerpts. To provide actionable, comparable feedback across assignments, it grades the attempt on a **0–5 rubric across three independent axes**:

1. **Correctness (0–5)**: Does the draft reach the right mathematical conclusion through valid logic?
2. **Rigor (0–5)**: Is every step formally justified? Are edge cases, degenerate conditions (such as ties or vacuous truths), and required assumptions explicitly addressed?
3. **Course-Fit (0–5)**: Does the proof use the professor's idiosyncratic notation, framing, and definitions as reflected in the lecture notes, rather than generic web conventions?

Separating these three scores is essential. In graduate coursework, an attempt might be mathematically correct (5/5) but sloppy on edge cases (2/5 rigor), or rigorous but using notation from another textbook that your professor dislikes (2/5 course-fit).

Along with these scores, the model outputs a concise `gap_tag` (such as `vacuous-case-overlooked` or `fundamental-property-misunderstanding`). When tested live against a deliberately flawed econometric proof claiming "residuals are always positive," the system correctly scored it 0/5 across all dimensions and tagged the exact conceptual error.

---

### 5. Adversarial Verification and Long-Term Memory

Two additional mechanisms complete the pedagogical loop:

#### `/verify` — The Ungrounded Adversarial Cross-Check
Even grounded RAG models make algebraic mistakes. When you run `/verify`, the system hands the active problem to a stronger, ungrounded model (`gemini-3.6-flash`). Crucially, the verifier is **deliberately hidden from the prior answer and retrieved excerpts**. This prevents it from rubber-stamping the tutor's assumptions. The REPL displays both solutions side by side, leaving you as the human arbiter.

#### `.session_log` & Proactive Blind-Spot Warning
Every turn — question, hint, draft, scores, and verification — is appended to a structured, local JSONL log (`.session_log/<course>.jsonl`). 

When reviewing for an exam, running `/summarize` computes honest mathematical rubric averages across your homework sets and synthesizes a personalized study plan. More powerfully, in subsequent study sessions, the base `answer_question()` function loads recent gap tags and folds them into its prompt — proactively cautioning you if a new practice problem touches a concept you struggled with last week.

---

### Why This Matters

The debate around AI in education is currently polarized between those who view it as an inevitable cheating tool and those who view it as a panacea. 

Building this system demonstrated that the difference between an AI that harms learning and an AI that accelerates it comes down to **pedagogical architecture**:
- Constraining models with negative generation boundaries to preserve student struggle.
- Grounding feedback in actual classroom materials to teach domain-specific rigor.
- Tracking student error patterns over time to turn mistakes into durable comprehension.

When software is designed around the psychology of how humans actually learn, AI stops being a shortcut and becomes a genuinely empowering intellectual partner.
