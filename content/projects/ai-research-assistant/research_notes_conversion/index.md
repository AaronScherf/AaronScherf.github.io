---
title: Research Notes Conversion
date: 2026-09-01
lastmod: 2026-10-16
summary: "Make Word research notes searchable alongside papers, with paragraph references that help locate the original argument."
type: ai-research-assistant-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/pipelines/convert_essays
  - type: site
    icon: brands/github
    label: 'Status: Research Notes Conversion'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/convert_essays/2026-09-01-research-notes-conversion-status.md
image:
  caption: "Word document structure is retained as searchable text with useful source locators."
tags:
  - Python
  - LLM / RAG
  - Vector Database
params:
  subproject:
    id: convert_essays
    package: pipelines/convert_essays
    code_paths:
      - ai-sandbox/academic-rag-model/pipelines/convert_essays
    readme_path: ai-sandbox/academic-rag-model/pipelines/convert_essays/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/convert_essays/2026-09-01-research-notes-conversion-status.md
        role: current
        lifecycle_ids:
          - research-notes-conversion
    members: []
---

An old research idea is easier to revisit when I can find it beside the papers that discuss the same topic. Research Notes Conversion brings Word essays and research notes into that search collection. It reads the document's existing headings and formatting directly, so the conversion itself needs neither image recognition nor an AI model.

<!--more-->

Finding a passage also needs a useful locator. Word documents do not carry the PDF page markers the search tools originally expected. The indexer now uses headings where available and paragraph numbers as a fallback, so a short note can be cited without inventing a page number.

[[Insert Image: Show a generic Word research-note outline becoming searchable text, with a highlighted passage and a locator "Paragraphs 4–6". Include a paper beside it in the search collection. Use invented content such as "Research idea" and "Possible comparison", not personal essays or a fabricated application interface. Suggested caption: "Find a research idea again, with a reference to its place in the note." Suggested alt text: "A Word note and a paper appear in the same collection; a selected note passage has a paragraph locator." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

For an **illustrative conversion**, a heading such as **Research idea** and its following paragraphs become a heading and ordinary text in the searchable version. A reference such as **Paragraphs 4–6** tells me where to look within that note. This demonstrates the format, not an excerpt from my private writing.

The original Word file stays in place. Conversion creates a Markdown copy, retaining headings, emphasis, and lists. Optional indexing then summarizes and embeds the document using API calls; conversion alone remains local.

Reusing the course-material indexer exposed a useful mismatch: its original document labels tried to classify personal essays as textbooks or handwritten notes. Giving the research collection its own vocabulary fixed that distinction. Search also keeps each result's collection identity, so two folders both named "notes" cannot be confused merely because their names match.

The early validation used 19 essay and research-note files. After the classification and locator fixes, topic queries could search this collection and Academic Hub together, returning relevant material from the appropriate sources. That is a limited recorded trial, not evidence that every query will find everything relevant.

The converter still works on selected local files. Direct Google Drive ingestion and a complete literature-review workflow are beyond its current interface. [Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/) adds papers to the same search infrastructure; the [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/convert_essays/README.md) documents conversion and indexing options.
