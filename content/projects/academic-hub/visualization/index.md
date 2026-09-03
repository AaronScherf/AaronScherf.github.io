---
title: Visualization Sub-Agent
date: 2026-09-03
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/viz
tags:
  - Python
  - LLM / RAG
---

An opt-in layer on top of the tutoring agent that generates an interactive Plotly visualization for a question's concept — a keyword-matched template library first, a local Ollama model as a free fallback for everything else, so a student gets a plot to manipulate alongside a cited text answer.

<!--more-->

Two tiers, both free of any paid API call: a handful of hand-written Plotly templates (spectral decomposition, gradient descent, distribution shape, series convergence) matched by keyword against the question, and — only when nothing matches — a local `qwen2.5-coder:7b` model prompted to write its own Plotly script for the concept, extracted, executed in a subprocess, and cached. That second tier is the one that has to actually work for "any topic," since a handful of templates can never cover a full course's syllabus the way a working code-generation path can.

Real usage surfaced real problems the unit tests couldn't. The Ollama-generated code produced schema-invalid Plotly properties on its first two live trials — a small local coder model writing unsupervised Plotly code is a genuine reliability risk, not a hypothetical one. It was hardened with a bounded validate-and-retry loop (each retry gets the previous attempt's exact code and error fed back as a corrective prompt) plus a tightened base prompt steering away from the specific class of property mistake both failures hit. A second live failure, sharper and less obvious: a slow-but-live Ollama call was indistinguishable from a genuinely unreachable one, so it got exactly one shot at a 180-second timeout instead of the retry budget the design intended — fixed by having the HTTP layer return a distinct timeout signal the retry loop can act on differently from a real connection failure. Two previously-failing real questions — "explain the intermediate value theorem" and a request for an eigenvectors/eigenvalues lesson — both now succeed end to end, one from the prompt fix alone, the other only after the timeout fix specifically.

A third, quieter bug came from template matching being *too* eager rather than not eager enough: bare keywords like `"convergence"` and `"divergence"` matched real, unrelated questions ("convergence in probability," the divergence theorem), silently handing them a wrong plot and skipping the fallback that would have had a real shot at the actual concept. And a genuinely dangerous one, caught before it saw real traffic: the subprocess running LLM-generated code inherited the parent process's full environment, including a paid API key it never legitimately needed — closed by giving that subprocess a minimal, explicit environment and its own scratch working directory instead.

**Currently a standalone `.html` file, not a combined report.** The visualization is returned as a bare file path alongside the tutor's separately-printed text answer and citation list — nothing today stitches the explanation, its citations, and the interactive plot into one document a student would actually want to hand someone. That's the deliberate next step, not an oversight: get the two tiers working reliably first, on real questions, before building a presentation layer on top of output that wasn't trustworthy yet.

Part of **Academic Hub**, built directly on top of **[RAG Analysis](/projects/academic-hub/rag_analysis/)**'s retrieval and citation grounding — the visualization agent reuses that agent's retrieved passages as context for the fallback tier, and is invoked as one opt-in parameter on the same `answer_question()` call.
