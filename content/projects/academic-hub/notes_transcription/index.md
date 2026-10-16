---
title: Notes Transcription Pipeline
date: 2026-08-27
lastmod: 2026-10-16
summary: "Turn handwritten and typed course materials into searchable notes, preserving a path back to the original pages."
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/pipelines/transcribe_notes
  - type: site
    icon: brands/github
    label: 'Status: Notes Transcription'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/transcribe_notes/2026-08-24-notes-transcription-status.md
tags:
  - Python
  - LLM / RAG
  - Hugging Face
image:
  caption: "Course pages and handwritten drawings become searchable text with source references."
params:
  subproject:
    id: transcribe_notes
    package: pipelines/transcribe_notes
    code_paths:
      - ai-sandbox/academic-rag-model/pipelines/transcribe_notes
    readme_path: ai-sandbox/academic-rag-model/pipelines/transcribe_notes/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/transcribe_notes/2026-08-24-notes-transcription-status.md
        role: current
        lifecycle_ids:
          - notes-transcription
    members: []
---

A question scribbled beside a lecture slide is easy to lose in a folder of drawings. Notes Transcription turns handwritten canvases and short course PDFs into searchable text, keeping references to the original material. It also separates pasted slides from handwriting, so later study tools can tell which explanation came from the lecturer and which note I added.

<!--more-->

Typed PDFs need care too. A small raised character can carry the difference between R² and R2, yet ordinary text extraction may flatten them into the same line. The pipeline uses character size and vertical position to recover exponents and subscripts locally before deciding whether a page needs AI transcription. That preserves useful structure without paying a model to reread every clean page.

[[Insert Image: Show an illustrative handwritten margin question beside a generic slide, then its searchable transcription with separate "Slide" and "Handwritten" labels and a source reference. Add a small inset comparing R² with flattened R2. Use invented notes, large labels, and no private coursework. Suggested caption: "Keep the handwriting, slide text, and source trail distinct." Suggested alt text: "A handwritten question and slide become separately labelled searchable text; an inset shows a preserved exponent." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

## Choose how much of the source needs rereading

The PDF path uses three levels of work. Clean digital text can be extracted locally. If only a few pages look defective, those pages receive image-based repair with neighboring text for context. Handwriting, difficult exports, or documents with widespread defects need fuller transcription. Some note-taking exports can omit entire equation regions from their text layer, so an apparently clean extraction is insufficient evidence for trusting them.

The recorded August 2026 comparison checked recovered exponents and subscripts across 13 pages from two documents against existing transcriptions. In one 43-page problem set, the local improvements reduced the detected defect rate from 63% to 5%, leaving two pages for repair. Those results concern the checked notation and routing decisions, not the accuracy of every word in the collection.

## Drawings and PDFs take different paths

Excalidraw saves its SVG images automatically. The canvas path cuts a tall drawing at whitespace gaps, transcribes the pieces with some preceding context, and produces both a raw transcript and an expanded note for search. Expansion adds prose and can introduce interpretation; the raw version and source drawing remain important for checking it. Handwritten questions can be marked for a separate answering tool.

The current command-line workflow can prepare page images and task cards for a subscription agent, then validate the submitted cards before writing the usual outputs. This is a manual handoff. The metered API path is also available, and search indexing has its own API calls; running the scripts locally does not mean all processing stays on the device.

Supported sources here are PDFs and Excalidraw scenes with exported images. Word-produced PDFs fit the PDF route; native Word documents are a separate conversion task. Most importantly, plausible-looking errors can survive transcription. [Notes Post-Processing](/projects/academic-hub/postprocess_notes/) checks suspicious text against source images afterward, while the [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/transcribe_notes/README.md) explains the available routes.
