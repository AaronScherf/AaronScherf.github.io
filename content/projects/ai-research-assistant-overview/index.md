---
title: AI Research Assistant
summary: "Find relevant papers, make their contents searchable, and look across them alongside personal research notes."
date: 2026-09-01
lastmod: 2026-10-16
image:
  caption: 'How paper discovery, document conversion, and search connect research materials'
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

AI Research Assistant brings paper discovery, document conversion, and search into the same research workflow. It can compare candidate abstracts with a description of my research question before trying to obtain the full articles. Converted papers can then be searched alongside my own research notes using the tools developed for Academic Hub.

<!--more-->

For an **illustrative research question** such as "How do researchers measure displacement after a disaster?", the starting point is more specific than a keyword search for disasters. I can ask the discovery tool to favor empirical measurement over policy commentary, then inspect the candidates before building a reading collection.

The three current tools handle different parts of that work:

1. **[Find candidate papers](/projects/ai-research-assistant/journal_discovery/).** Search an academic-publication catalog by researcher or topic, then score abstracts against the research description using a model running locally. The tool tries several sources for full text and records papers that need manual retrieval. Finding a relevant paper does not guarantee access to it.
2. **[Make articles searchable](/projects/ai-research-assistant/journal_article_transcription/).** Convert available PDFs to text with references back to their pages. The converter reuses the course-notes tools, choosing local extraction or AI transcription according to the document. Equations, figures, and imperfect extraction still need checking.
3. **[Bring in research notes](/projects/ai-research-assistant/research_notes_conversion/).** Convert Word documents, including research ideas and application essays, while retaining headings and basic formatting. Their text and the papers enter the same search catalog, making it possible to look for a topic across both.

The shared search tools can also query the research collection and Academic Hub's course materials together. Each collection keeps its own records, so a paper and a lecture note remain distinguishable when both match a question.

These tools support a literature review that I direct: choosing the question, reviewing papers, obtaining restricted articles, and interpreting the evidence remain part of my work. The [subproject pages](/projects/ai-research-assistant/) give the current capabilities and limits of each stage.
