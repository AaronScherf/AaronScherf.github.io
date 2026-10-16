---
title: Marker PDF Conversion
date: 2026-08-19
lastmod: 2026-10-16
summary: "Convert mathematical textbooks into searchable study material, with chapter structure, figure descriptions, and references back to the book."
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/pipelines/convert_textbook
  - type: site
    icon: brands/github
    label: 'Status: Textbook Conversion'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/convert_textbook/2026-09-10-textbook-conversion-status.md
  - type: site
    icon: brands/github
    label: 'Status: Chapter Aware Chunking'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/convert_textbook/2026-08-22-chapter-aware-chunking-status.md
  - type: site
    icon: brands/github
    label: 'Status: Image Description'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/convert_textbook/2026-08-23-image-description-status.md
tags:
  - Python
  - Google Cloud Platform
  - LLM / RAG
image:
  caption: "Textbook conversion preserves chapter boundaries and references back to source pages."
params:
  subproject:
    id: convert_textbook
    package: pipelines/convert_textbook
    code_paths:
      - ai-sandbox/academic-rag-model/pipelines/convert_textbook
    readme_path: ai-sandbox/academic-rag-model/pipelines/convert_textbook/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/convert_textbook/2026-09-10-textbook-conversion-status.md
        role: current
        lifecycle_ids:
          - textbook-conversion
      - path: ai-sandbox/academic-rag-model/docs/status/convert_textbook/2026-08-22-chapter-aware-chunking-status.md
        role: current
        lifecycle_ids:
          - chapter-chunking
      - path: ai-sandbox/academic-rag-model/docs/status/convert_textbook/2026-08-23-image-description-status.md
        role: current
        lifecycle_ids:
          - image-description
    members: []
---

Finding a word in a textbook PDF does not necessarily find the argument around an equation or the information inside a diagram. Marker PDF Conversion prepares those books for the study tools in Academic Hub: searchable text, mathematical notation, extracted figures, and references back to the source pages. A separate description pass makes figures easier to find through text search too.

<!--more-->

Where a long book is divided matters. A fixed page limit can cut through a table or a proof, so the converter looks for chapter boundaries in the PDF outline or printed contents first. It also distinguishes the PDF's page position from the page number printed in the book. That lets a reference such as "see page 157" remain useful even when a preface has shifted the file's numbering.

[[Insert Image: Show a generic textbook spread becoming a chapter-organized text excerpt and a figure description. Highlight separate "PDF page" and "Printed page" labels, with an illustrative cross-reference that points back to the correct source page. Use newly typeset material and a simple invented diagram, not a private textbook crop. Suggested caption: "Preserve the structure needed to find and check a passage." Suggested alt text: "A textbook chapter, equation, and figure become searchable text with both PDF and printed-page references." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

## Rent the hardware for the batch

Marker is an open-source tool for recognizing text and page layout. Here it runs on a temporary graphics-processing machine in Google Cloud, which provides the computing capacity needed for dense books. The model loads once for a batch rather than starting again for every title. Converted files return locally before the temporary machine and disk are removed; keeping an idle disk would continue to cost money.

This is the heavier conversion route. Short documents and handwriting use [Notes Transcription](/projects/academic-hub/notes_transcription/) instead. The inputs are source PDFs I am authorized to process for my own study; the website does not distribute those books.

## Keep the source available for comparison

In the recorded four-book check, printed-page labels were recovered for roughly 96-98% of pages, with no duplicate internal anchors. That is encouraging coverage across those layouts, with gaps still requiring the PDF page reference. It does not establish that every formula or cross-reference was transcribed correctly.

The separate figure pass described 764 of 793 candidate images across five books, skipping 29 as decorative. Its derived text leaves the original conversion intact. Descriptions make a chart discoverable but cannot replace examining its axes, values, or visual argument in the source.

Before spending GPU time, duplicate checks can reuse an existing conversion. Less certain matches remain subject to review. Recovery from memory failures also has a documented retry and escalation policy, tested separately from the content checks; those tests do not establish reliability across every cloud interruption.

The [conversion README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/convert_textbook/README.md) covers operation and costs. The page's linked status records document the conversion, chapter, and figure trials.
