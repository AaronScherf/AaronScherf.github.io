---
title: Notes Post-Processing
date: 2026-08-28
lastmod: 2026-10-16
summary: "Find plausible-looking extraction errors by checking suspicious text against the original page image."
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/pipelines/postprocess_notes
  - type: site
    icon: brands/github
    label: 'Status: Notes Postprocessing'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/postprocess_notes/2026-08-27-notes-postprocessing-status.md
image:
  caption: "Suspicious extracted text is compared with its source page before correction."
tags:
  - Python
  - Hugging Face
  - LLM / RAG
  - Machine Learning
params:
  subproject:
    id: postprocess_notes
    package: pipelines/postprocess_notes
    code_paths:
      - ai-sandbox/academic-rag-model/pipelines/postprocess_notes
    readme_path: null
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/postprocess_notes/2026-08-27-notes-postprocessing-status.md
        role: current
        lifecycle_ids:
          - notes-postprocessing
    members: []
---

A square-root sign once became the letter p in my extracted notes. The text still looked printable and ordinary, so the initial checks let it through. Notes Post-Processing was built to catch that kind of plausible-looking error after transcription, then compare it with the original page before making a correction.

<!--more-->

Context on both sides of a symbol mattered. Looking only at the text before the corrupted character missed evidence that appeared afterward; a second local model could use that surrounding context to judge which positions deserved attention. The models flag candidates rather than deciding what the source must have said.

[[Insert Image: Create a close comparison of an illustrative source formula, the mistaken extraction "p(h² + k²)", and the corrected "√(h² + k²)". Highlight only the first symbol. Show a source-page comparison between detection and correction, using a newly typeset example rather than an unapproved private page crop. Suggested caption: "One ordinary-looking letter can change the meaning of an equation." Suggested alt text: "The letter p in extracted text is replaced with a square-root sign after comparison with the source formula." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

The recorded motivating run repaired that square-root error on page 6 and left nine other flagged candidates unchanged. The notation below illustrates the difference:

| Extracted text | Corrected reading |
| --- | --- |
| `p(h² + k²)` | `√(h² + k²)` |

The tool first identifies suspicious text using structural checks and local language-model scores. Surviving candidates go to an image-based comparison with the PDF page. It records whether the page was changed, left alone, or could not be verified.

Testing across more notes exposed another problem: legitimate mathematical language can look unusual to a general language model. Joined words from an upstream spacing error also produced many false alarms. Fixing the spacing and tuning the checks reduced unnecessary flags, but did not eliminate them.

False positives consume review time and image-checking calls. Comparing with an image supplies additional evidence; the model can still misread that evidence or make a bad change. Corrected material therefore needs spot checks rather than being treated as automatically clean.

This tool follows [Notes Transcription](/projects/academic-hub/notes_transcription/) and helps improve material used by the [Source Indexer](/projects/academic-hub/source_indexer/). The [status and validation record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/postprocess_notes/2026-08-27-notes-postprocessing-status.md) describes the reproduced error and broader precision limits.
