---
title: Source Indexer
date: 2026-08-30
lastmod: 2026-10-16
summary: "Find relevant course documents and passages, with references that study tools can use and readers can inspect."
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/core/indexer
  - type: site
    icon: brands/github
    label: 'Status: Source Indexer'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/indexer/2026-08-29-source-indexer-status.md
  - type: site
    icon: brands/github
    label: 'Status: Passage Embeddings'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/indexer/2026-08-29-passage-embeddings-status.md
  - type: site
    icon: brands/github
    label: 'Status: Cross Offering Linkage'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/indexer/2026-10-03-cross-offering-linkage-status.md
tags:
  - Python
  - LLM / RAG
  - Vector Database
image:
  caption: "Illustration: find the document, then the passage worth reading."
  alt_text: "An illustrative question narrows from course records to documents and a source-referenced passage."
  focal_point: Center
params:
  subproject:
    id: source_indexer
    package: core/indexer
    code_paths:
      - ai-sandbox/academic-rag-model/core/indexer
    readme_path: ai-sandbox/academic-rag-model/core/indexer/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/indexer/2026-08-29-source-indexer-status.md
        role: current
        lifecycle_ids:
          - source-indexer-core
      - path: ai-sandbox/academic-rag-model/docs/status/indexer/2026-08-29-passage-embeddings-status.md
        role: current
        lifecycle_ids:
          - passage-embeddings
      - path: ai-sandbox/academic-rag-model/docs/status/indexer/2026-10-03-cross-offering-linkage-status.md
        role: current
        lifecycle_ids:
          - cross-offering-linkage
    members: []
---

A question about eigenvalues might belong with a textbook proof, a lecture explanation, or an exercise I have already attempted. Source Indexer searches converted course materials in two stages: first finding promising documents, then locating passages inside them. The result includes a heading, page, or paragraph reference so I can continue reading where the match came from.

<!--more-->

The search catalog has a record for each document, much like a library card with a brief description and subject labels. These descriptions help find material; the longer summaries I study are written by the answering and guide tools. A record's identity comes from the source file's contents rather than its filename, so renaming a PDF does not have to create a new document. Course-level records narrow the search before it compares individual files.

## Give other study tools something to read

The [notes](/projects/academic-hub/notes_transcription/) and [textbook](/projects/academic-hub/marker_conversion/) converters register their outputs with the indexer. Search uses document descriptions, subject labels, and numerical representations of meaning to rank related material, then returns excerpts from selected documents. PDF-derived passages can carry page references; Word-derived notes without page markers can use headings or numbered paragraphs instead.

Several study tools use that foundation:

- [RAG Analysis](/projects/academic-hub/rag_analysis/) retrieves passages for a question and records their references with the answer. [Summary Enhancement](/projects/academic-hub/summary_enhancement/) can reopen the exact passages saved with a study summary to develop it further.
- [Study Guide Pipeline](/projects/academic-hub/study_guide_pipeline/) selects indexed sources for a topic list, then drafts and revises a longer guide.
- [Concept Graph](/projects/academic-hub/concept_graph/) retrieves evidence for explanations and connections, including the conditions a theorem needs.

The same search infrastructure supports [papers and research notes](/projects/ai-research-assistant-overview/), keeping their collection identities distinct from course materials. Each downstream tool still has to interpret the passages it receives.

## Similar subjects are not always duplicate notes

A lecture may exist as handwriting alone and as a later version with slides pasted beside the same handwriting. Searching both can crowd out other useful sources. Whole-document similarity was too broad to distinguish these pairs from different lectures on the same subject. The subset linker instead compares short word sequences from the handwritten portions, then hides the smaller version when its fuller counterpart survives the search. Both remain accessible.

Links across different years of a course are another feature. The tool reuses existing document comparisons to identify related material, with uncertain matches held for review. That supports revisiting an older explanation without claiming every note has already been matched correctly.

An early August 2026 checkpoint recorded 30 healthy document cards in one course, with 14 subject labels. Those are historical catalog checks, not current totals or a measure of search accuracy. Dense proofs and narrative notes can still need different passage boundaries. [Corpus Health](/projects/academic-hub/corpus_health/) can report missing or stale outputs, but its available repair is narrowly scoped rather than a general automatic cleanup. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/core/indexer/README.md) describes the catalog, search, and linking behavior.
