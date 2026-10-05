---
title: Academic Hub
date: 2026-09-01
image:
  caption: 'Comprehensive architecture of the Academic Hub ecosystem across sources, pipelines, vault, and tutoring agents'
  image_suggestion: "System overview diagram of the entire Academic Hub ecosystem: illustrating raw academic inputs (textbooks, handwritten notes, lecture videos) passing through ingestion pipelines into a standardized Markdown knowledge base, structured indexing cards, and the downstream AI tutoring agent suite with interactive visualizations and problem generation."
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

*Figure: Academic Hub ecosystem architecture showing ingestion and processing pipelines connecting raw academic sources to the Markdown knowledge vault and downstream tutoring agent suite.*

Twelve subprojects currently make up the hub across conversion, indexing, and tutoring layers:

- **[Marker PDF Conversion](/projects/academic-hub/marker_conversion/)** — turns dense, math-heavy textbooks into clean, LLM-ready Markdown using a GPU-rented pipeline built around chapter-aware chunking.
- **[Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/)** — the GPU-free sibling that handles short, messy academic material: TA notes, problem sets, exams, and handwritten scans with 3-tier cost routing.
- **[Notes Post-Processing](/projects/academic-hub/postprocess_notes/)** — downstream ML anomaly-detection pass using causal surprisal and masked-LM scoring to catch silent extraction corruptions before visual image verification.
- **[Obsidian Git Sync](/projects/academic-hub/obsidian_git_sync/)** — syncs Excalidraw handwritten lecture notes between tablet and laptop via lightweight GitHub API integration, paired with lexical subset-linking in the indexer.
- **[Source Indexer](/projects/academic-hub/source_indexer/)** — turns the growing pile of converted documents into a searchable, tagged corpus with two-stage retrieval.
- **[RAG Analysis](/projects/academic-hub/rag_analysis/)** — the grounded, citation-backed question-answering agent built on top of that retrieval layer.
- **[Tutor Diagnosis & Hint Generator](/projects/academic-hub/tutor_diagnosis/)** — pedagogical problem-set tutor with non-spoiler hint generation, 3-axis draft evaluation, and independent verification.
- **[Problem Corpus Extraction](/projects/academic-hub/problem_corpus/)** — extracts structured practice problems with honest provenance from problem sets and textbooks into an indexed question bank.
- **[Problem Generation Sub-Agent](/projects/academic-hub/problem_generation/)** — generates targeted practice problems and worked solutions with split-verdict technique and correctness verification.
- **[Visualization Sub-Agent](/projects/academic-hub/visualization/)** — an opt-in layer that generates an interactive Plotly visualization alongside a tutor answer, with a template library and local coder fallback.
- **[Audio Generator](/projects/academic-hub/audio_generator/)** — narrates course notes into listenable podcast-length MP3 episodes with LaTeX density routing and multi-worker Piper TTS.
- **[Video Lecture Notes](/projects/academic-hub/video_notes/)** — transcribes and synthesizes YouTube lecture playlists into structured Markdown notes with clickable timestamp citations.

Browse all twelve subprojects on the **[Academic Hub subprojects page](/projects/academic-hub/)**.
