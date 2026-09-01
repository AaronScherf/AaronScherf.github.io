---
title: RAG Analysis
date: 2026-08-30
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/rag
tags:
  - Python
  - LLM / RAG
---

A grounded question-answering agent that retrieves and cites real passages from the textbooks and notes produced by the Marker PDF Conversion and Notes Transcription pipelines — usable directly as a multi-turn chat, or as a stateless function other agents can call.

<!--more-->

The core of it is a single function, `answer_question()`, deliberately stateless per call: conversation history is an explicit input and output the caller owns, not internal session state. That one design choice is what lets it serve two different usage modes without two separate implementations — an interactive REPL that threads history across turns, and a plain callable a larger pipeline can invoke once and use the result from, the same way a study-plan agent might eventually hand it a course syllabus and ask for a grounded read on a topic. Inside a call: a follow-up question first gets condensed into a standalone, retrievable query using recent history (skipped entirely on the first turn), the reformulated question goes to the source indexer's existing passage-level search, a diversification step caps how many top-ranked passages can come from a single file so a comparative question actually pulls from multiple sources instead of one dominant document crowding out the rest, and generation is prompted to answer using *only* the retrieved excerpts — citing each one inline and saying so plainly when the excerpts don't cover the question, rather than filling the gap from general knowledge.

Retrieval itself isn't new machinery built for this agent — it's the passage-level search already shipped as part of the **[Source Indexer](/projects/academic-hub/source_indexer/)** subproject, reused as-is. That's a deliberate sequencing choice: file-level relevance ("which document") and passage-level relevance ("which paragraph actually answers this") are different problems, and building the second on top of an already-validated first meant this agent could focus entirely on reformulation, diversification, and grounded generation instead of re-solving retrieval from scratch.

Run for real, not just unit-tested: a live query — "what is the spectral theorem" — produced a substantive, correctly-cited answer synthesizing content from two different files at once (a lecture-note document and a separate linear algebra textbook), each citation a real, checkable theorem and page reference. A full multi-turn exchange confirmed history accumulates correctly across turns and that the reformulation step produces a genuinely on-topic standalone question from a vague follow-up ("explain that differently" → a specific, correctly-scoped restatement of the original question for a beginner). A real side-by-side model comparison — `gemini-3.6-flash` against the project's cheaper default tier, `gemini-3.1-flash-lite` — found no meaningful quality or coverage difference on the same question, so the original choice (picked on an untested "tutoring needs more reasoning" heuristic) was reversed in favor of the cheaper model once actually measured against real output.

Not every finding closed cleanly. One real run during multi-turn testing produced an answer citing files that didn't reappear in a direct re-run of retrieval for the same, correctly-reformulated query — diagnosed as far as the evidence allowed (the reformulation and the retrieval were each independently confirmed correct), but not fully explained. The most likely cause is temperature=0 not being perfectly deterministic server-side, especially with many real passages scoring closely together (0.68–0.74, a tight cluster where a slightly different phrasing could plausibly reorder results) — recorded as a known, real source of run-to-run variance rather than quietly assumed away.

Some things this agent is explicitly *not* built for yet, and why that's a real scope boundary rather than an oversight: it has no persistent memory across process runs, so a scheduled task that needs to know what it already covered yesterday has nothing to build on until that's added; its retrieval pulls a small, fixed number of passages for one question, which is workable for "summarize chapter 7" but untested and likely too narrow for "summarize everything I've covered this week"; and its own anti-hallucination guardrail — never introduce a claim the retrieved excerpts don't support — is correct for tutoring but actively works against generating a genuinely new problem set, since a new problem is by definition not sitting verbatim in any retrieved passage. Each of these is a distinct, scoped follow-on rather than a flaw in what already works.

Part of **Academic Hub**, the broader knowledge network combining this agent with **[Marker PDF Conversion](/projects/academic-hub/marker_conversion/)**, **[Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/)**, and the **[Source Indexer](/projects/academic-hub/source_indexer/)** into a single ecosystem for domain-tuned AI assistants.
