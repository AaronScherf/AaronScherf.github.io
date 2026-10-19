---
title: Journal Article Transcription
date: 2026-09-01
lastmod: 2026-10-16
summary: "Make article contents searchable with page references, while retaining a route back to figures, equations, and the original PDF."
type: ai-research-assistant-project
image:
  caption: "Illustration: Search converted text, then return to the source page to check it."
  alt_text: "An invented journal PDF page and its matching searchable paragraph share a page-four locator; the original equation and figure remain available to inspect."
  focal_point: Center
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/pipelines/convert_journal_articles
  - type: site
    icon: brands/github
    label: 'Status: Journal Article Transcription'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/convert_journal_articles/2026-09-01-journal-article-transcription-status.md
tags:
  - Python
  - LLM / RAG
params:
  subproject:
    id: convert_journal_articles
    package: pipelines/convert_journal_articles
    code_paths:
      - ai-sandbox/academic-rag-model/pipelines/convert_journal_articles
    readme_path: ai-sandbox/academic-rag-model/pipelines/convert_journal_articles/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/convert_journal_articles/2026-09-01-journal-article-transcription-status.md
        role: current
        lifecycle_ids:
          - journal-transcription
    members: []
---

Finding a paper is only the start; later I need to locate the argument, method, or result inside it. Journal Article Transcription converts available article PDFs into searchable text with references back to their pages. A paper's contents can then appear beside my research notes in a search result.

<!--more-->

The converter reuses the same machinery as the [Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/). Clean digital text can be extracted locally; harder pages need transcription from their images. The current default prepares task cards for an agent working through my subscription, then validates submitted work before writing and indexing it. Search summaries and embeddings still use API calls, even on that transcription route.

A separate metered-API route remains available. Pending agent work stays pending unless API fallback is explicitly requested; it is not silently sent for paid transcription. Very long documents are flagged for a person's decision rather than automatically sent to the more expensive textbook converter.

The older September 2026 trial converted and indexed three distinct papers. A fourth file was an exact duplicate, and a topic query found the relevant papers alongside the essay collection. Those results establish the earlier conversion-and-search path; they are not a new live trial of the subscription task-card workflow.

Page references make checking easier, but converted prose cannot preserve everything a figure communicates. Equations, chart labels, and extraction errors still deserve comparison with the PDF.

PDFs can come from [Journal Discovery](/projects/ai-research-assistant/journal_discovery/) or files I add myself. Conversion registers their text with the [Source Indexer](/projects/academic-hub/source_indexer/); [Research Notes Conversion](/projects/ai-research-assistant/research_notes_conversion/) brings Word documents into that same collection. The [current README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/convert_journal_articles/README.md) describes the task-card and API routes.
