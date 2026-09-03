---
title: Problem Generation Sub-Agent
date: 2026-09-03
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/specs/2026-09-03-problem-generation-design.md
tags:
  - Python
  - LLM / RAG
---

Designed but not yet built: a peer of the **[Visualization Sub-Agent](/projects/academic-hub/visualization/)** that would generate a new practice problem plus a worked solution — styled after the student's own problem sets and exams, grounded in their own textbooks — the moment a question sounds like a request for practice rather than an explanation.

<!--more-->

The plan mirrors the visualization agent's shape deliberately: a new `problem_gen/` package, generation via a local Ollama model only (no paid API call, same constraint and same reasoning as the viz fallback), and graceful fallback to the tutor's normal question-answering whenever generation isn't available — never a hard dependency. Where it diverges is retrieval. Two separate pools get pulled per request: the student's own real problems on the topic (`doc_type="problem_set"`, already chunked one-problem-per-chunk by the indexer's existing numbered-problem detection) as the style and difficulty anchor, and real textbook passages (`doc_type="textbook"`) as the correctness anchor. An empty style pool returns nothing rather than generating an ungrounded problem — there's no point styling one after examples that don't exist — while an empty content pool just proceeds on style alone, since a topic can plausibly still generate correctly without textbook grounding.

Course resolution gets a tighter rule than plain Q&A's own: rather than trusting the top-3 similarity-based course candidates that citations tolerate fine, a free-text mention ("for my microeconomics course") is checked directly against the corpus's own known course list first, since one stray problem pulled from a semantically-adjacent but wrong course — wrong notation, wrong level — would actively corrupt what gets generated in a way a stray citation never does. Generation itself is a two-call loop: one call asks for a new problem and worked solution (explicitly not a copy of the retrieved examples) in the style/notation of the retrieved problems; a second, separate call hands the model back its own problem and solution and asks it to verify correctness before anything is returned. Failure at either step — extraction fails, or verification comes back `INVALID: <reason>` — feeds that exact failure into a retry, capped at three attempts, the same pattern already validated live in the visualization agent's own retry-hardening pass. Nothing is cached: every request generates fresh, so asking for "another one" is simply another call rather than a repeat.

Integration is automatic rather than a special command: a cheap regex intent check on the tutor's own question text (`"give me a problem"`, `"quiz me"`, `"another exercise"`, and similar phrasing) routes a matching question to this subagent instead of the normal retrieval-and-answer flow, falling straight through to ordinary Q&A on the same question if generation returns nothing. The one piece of shared infrastructure this pass would also extract: `viz/llm_fallback.py`'s Ollama HTTP-call helper and its unreachable-vs-timeout distinction (the retry-worth-it call this project already got right once, the hard way) move into a small shared `common/ollama_utils.py` rather than being duplicated a second time in the same codebase the same week.

**Nothing beyond the design and implementation plan exists yet** — no `problem_gen/` package, no shared Ollama helper, no live test against the math-tuned model this would use (`qwen2.5-math:7b`, distinct from the viz agent's code-tuned `qwen2.5-coder:7b`). Full design: [`docs/superpowers/specs/2026-09-03-problem-generation-design.md`](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/specs/2026-09-03-problem-generation-design.md); implementation plan: [`docs/superpowers/plans/2026-09-03-problem-generation-plan.md`](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/plans/2026-09-03-problem-generation-plan.md). This page will get real status updates once building starts, the same way **[Visualization Sub-Agent](/projects/academic-hub/visualization/)**'s did.

Part of **Academic Hub**, built directly on top of **[RAG Analysis](/projects/academic-hub/rag_analysis/)**'s retrieval layer and reusing the **[Source Indexer](/projects/academic-hub/source_indexer/)**'s existing `doc_type` filtering rather than adding a new one.
