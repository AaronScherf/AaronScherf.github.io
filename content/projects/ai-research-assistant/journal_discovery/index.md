---
title: Journal Discovery Pipeline
date: 2026-09-02
lastmod: 2026-10-16
summary: "Find papers for a research question, obtain available full text, and keep a clear handoff for papers that need library access."
type: ai-research-assistant-project
image:
  caption: "Illustration: Finding a relevant paper and obtaining its full text are separate steps."
  alt_text: "One disaster-research trial narrowed 60 candidates to 15 accepted papers, with seven PDFs downloaded and eight left for manual access."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/discovery/discover_journal_articles
  - type: site
    icon: brands/github
    label: 'Status: Journal Discovery (original build)'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/discover_journal_articles/2026-09-01-journal-discovery-status.md
  - type: site
    icon: brands/github
    label: 'Status: Journal Discovery (reliability, classification, validation)'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/discover_journal_articles/2026-10-15-reliability-classification-and-validation-status.md
tags:
  - Python
  - Hugging Face
  - LLM / RAG
params:
  subproject:
    id: discover_journal_articles
    package: discovery/discover_journal_articles
    code_paths:
      - ai-sandbox/academic-rag-model/discovery/discover_journal_articles
    readme_path: ai-sandbox/academic-rag-model/discovery/discover_journal_articles/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/discover_journal_articles/2026-09-01-journal-discovery-status.md
        role: historical
        lifecycle_ids:
          - journal-discovery
      - path: ai-sandbox/academic-rag-model/docs/status/discover_journal_articles/2026-10-15-reliability-classification-and-validation-status.md
        role: current
        lifecycle_ids:
          - journal-discovery
    members: []
---

A search for "disaster resilience" can return papers about infrastructure, recovery, public health, or business continuity. Journal Discovery lets me specify the angle I want, then compares that description with candidate abstracts before trying to download anything. The comparison runs locally, helping narrow a broad literature search without asking a language model to judge every paper.

<!--more-->

The October 15, 2026 trial makes the stages concrete: a disaster-research query retrieved 60 candidates, accepted 15 as relevant, and downloaded seven PDFs. Eight accepted papers still needed manual access. Finding a candidate, obtaining its full text, and reading or evaluating it are separate accomplishments; the pipeline handles the first two only within the available access routes.

## Grow a library around a question

The starting point can be a topic or a researcher's name. OpenAlex, an academic works catalog, supplies candidates and bibliographic information. A locally computed representation of each abstract is compared with my relevance description. When an abstract is unavailable, title-based scoring is a weaker signal; names and subject labels also need judgment.

A citation-following mode offers another route: find newer papers citing material already in the library, review the proposed list, then fetch the selected papers. A citation alone never authorizes that download step or establishes relevance.

The downloader tries open-access sources and the configured institutional route. If a publisher requires ordinary browser access, the paper goes onto a linked manual-download list. I use my library access in the browser and save the PDF; the tool does not solve publisher access challenges. Downloaded files are checked as PDFs and written through temporary files so an interrupted transfer does not leave a partial final file.

## Discovery is upstream of reading

[Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/) separately converts and indexes the files. Reconciliation can recognize manually saved papers by their converted contents, rather than depending on filenames.

Two maintenance operations have different authority. The older metadata audit can automatically reconcile mechanical folder and tag differences against its reference data, while flagging title or author mismatches. The newer classification mode uses stored OpenAlex Topics to propose folder and tag decisions for human acceptance. It is not an automatic reading of each paper's argument.

Direct inspection found the 15 accepted disaster papers on topic in that trial; a separate author query accepted six and downloaded one. Those are limited runs. Converted chart descriptions may also omit plotted values, so later search results still need checking against the PDF. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/discovery/discover_journal_articles/README.md) and linked October status record give the current workflow and evidence.
