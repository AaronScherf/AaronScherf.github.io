---
title: Academic Hub
date: 2026-09-01
image:
  caption: 'Comprehensive architecture of the Academic Hub ecosystem across sources, pipelines, vault, and tutoring agents'
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model
tags:
  - Python
  - LLM / RAG
params:
  subproject:
    id: academic_hub_overview
    package: null
    code_paths: []
    readme_path: null
    status_docs: []
    members:
      - source_indexer
      - transcribe_notes
      - convert_textbook
      - postprocess_notes
      - generate_video_notes
      - rag
      - tutor_diagnosis
      - socratic_tutor
      - visualization
      - problem_generation
      - problem_corpus
      - study_guide
      - summary_enhancement
      - audio_generator
      - corpus_health
      - project_steering
      - guided_solutions
      - obsidian_git_sync
      - concept_graph
---

Academic Hub is the broader knowledge network tying together everything below: converting dense textbooks and messy academic notes into clean Markdown, indexing and tagging the growing corpus, and serving grounded, cited answers back through a tutoring agent — one pipeline turning years of raw coursework into a queryable, AI-tutored knowledge base.

<!--more-->

The hub spans conversion, indexing, study workflows, tutoring, and corpus maintenance. The established project pages include:

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

The hub also includes [Socratic Tutor](/projects/academic-hub/socratic_tutor/), [Study Guide Pipeline](/projects/academic-hub/study_guide_pipeline/), [Summary Enhancement](/projects/academic-hub/summary_enhancement/), [Corpus Health](/projects/academic-hub/corpus_health/), [Project Steering](/projects/academic-hub/project_steering/), [Guided Solutions](/projects/academic-hub/guided_solutions/), and [Concept Graph](/projects/academic-hub/concept_graph/). These cover different stages of the work, from study workflows used on course material to tools with a narrower test or live-run record. Each page describes its evidence and remaining limits.

Browse the **[Academic Hub subprojects page](/projects/academic-hub/)** for the current published set.
