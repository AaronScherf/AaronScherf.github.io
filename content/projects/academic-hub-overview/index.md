---
title: Academic Hub
date: 2026-09-01
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model
tags:
  - Python
  - LLM / RAG
---

Academic Hub is the broader knowledge network tying together everything below: converting dense textbooks and messy academic notes into clean Markdown, indexing and tagging the growing corpus, and serving grounded, cited answers back through a tutoring agent — one pipeline turning years of raw coursework into a queryable, AI-tutored knowledge base.

<!--more-->

Six subprojects currently make up the hub, each documented on its own page:

- **[Marker PDF Conversion](/projects/academic-hub/marker_conversion/)** — turns dense, math-heavy textbooks into clean, LLM-ready Markdown using a GPU-rented pipeline built around chapter-aware chunking.
- **[Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/)** — the GPU-free sibling that handles short, messy academic material: TA notes, problem sets, exams, and handwritten scans.
- **[Source Indexer](/projects/academic-hub/source_indexer/)** — turns the growing pile of converted documents into a searchable, tagged corpus with two-stage retrieval.
- **[RAG Analysis](/projects/academic-hub/rag_analysis/)** — the grounded, citation-backed question-answering agent built on top of that retrieval layer.
- **[Visualization Sub-Agent](/projects/academic-hub/visualization/)** — an opt-in layer that generates an interactive Plotly visualization alongside a tutor answer, via a template library and a local, free LLM fallback, now with its own local example memory for few-shot prompting.
- **[Problem Generation Sub-Agent](/projects/academic-hub/problem_generation/)** — designed but not yet built: would generate a new practice problem and worked solution, styled after the student's own problem sets and grounded in their own textbooks.

Browse all six, with more detail on how they fit together, on the **[Academic Hub subprojects page](/projects/academic-hub/)**.
