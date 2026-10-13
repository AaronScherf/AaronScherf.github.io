---
title: AI Research Assistant
date: 2026-09-01
image:
  caption: 'AI Research Assistant software ecosystem architecture across inputs, pipelines, and vector retrieval'
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
    id: research_overview
    package: null
    code_paths: []
    readme_path: null
    status_docs: []
    members:
      - convert_essays
      - convert_journal_articles
      - discover_journal_articles
---

AI Research Assistant is the effort to search for, download, transcribe, embed, index, and analyze journal articles and personal research material — building a second, parallel knowledge corpus alongside Academic Hub, on the same source-indexing and retrieval infrastructure.

<!--more-->

Three subprojects are shipped so far, each documented on its own page:

- **[Journal Discovery Pipeline](/projects/ai-research-assistant/journal_discovery/)** — resolves a faculty name or research topic into full-text PDFs automatically, via OpenAlex, citation-based snowball sampling, and a five-tier open-access/EZProxy fetch chain, with a manual-download fallback and worklist for whatever a script can't reach on its own.
- **[Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/)** — a PDF pipeline for academic journal articles that reuses the Notes Transcription pipeline's tiered cost-routing wholesale.
- **[Research Notes Conversion](/projects/ai-research-assistant/research_notes_conversion/)** — a `.docx`-to-Markdown converter for PhD-application essays and loose research notes.

Browse the three shipped subprojects, with more detail on how they fit together, on the **[AI Research Assistant subprojects page](/projects/ai-research-assistant/)**.
