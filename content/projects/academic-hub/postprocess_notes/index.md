---
title: Notes Post-Processing
date: 2026-08-28
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/pipelines/postprocess_notes
image:
  caption: 'Notes Post-Processing pipeline with multi-stage structural filtering, local NLP surprisal scoring, and visual ground-truth verification'
tags:
  - Python
  - Hugging Face
  - LLM / RAG
  - Machine Learning
---

A downstream machine-learning verification and anomaly-detection pass over already-transcribed Markdown notes, catching silent character corruptions on pages that bypassed vision OCR models because their text layer appeared cleanly extracted.

<!--more-->

*Figure: Notes Post-Processing pipeline showing candidate generation via structural filters, two-stage local Hugging Face NLP scoring (causal GPT-2 surprisal and bidirectional DistilBERT masked-LM), and final visual ground-truth verification against cropped source PDF page images via Gemini.*

The **[Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/)** uses a three-tier cost router to avoid burning paid vision API calls on clean documents: files with a healthy digital text layer are extracted locally for free via `PyMuPDF`. But "clean-looking" text can conceal subtle, catastrophic extraction corruptions that rule-based regexes are blind to.

The motivating bug was discovered during a manual audit of real coursework: on page 6 of `Analysis_Exercises.pdf`, a square-root / radical symbol extracted as plain ASCII `p`. It was not an unprintable character, not a repeated sequence, and had no adjacent digits. To every regex heuristic in the extraction router, the page looked 100% clean and bypassed vision models entirely. Layering on ever-more specific regexes to catch individual glyph failures quickly becomes unmaintainable. Instead, `postprocess_notes.py` was built as a dedicated, downstream ML verification pass over already-generated Markdown.

The pipeline uses a multi-stage filtering architecture designed to run efficiently on local CPU:
1. **Structural Pre-Filter**: Scans for suspicious topological markers, such as an isolated single character standing alone on its own line or at an equation boundary — the exact footprint of a dropped mathematical delimiter.
2. **Causal Language Model Surprisal (GPT-2)**: Evaluates candidate positions using causal token perplexity z-scores, narrowing candidates without making network requests.
3. **Bidirectional Masked-LM Verification (DistilBERT)**: A critical architectural finding was that unidirectional causal models struggle with mathematical errors because the disambiguating context often appears *after* the corruption (e.g. `p(h^2 + k^2)` looks syntactically plausible from the left, but nonsensical when reading both directions). Bidirectional masked scoring provided clean separation between valid words and corrupt tokens.
4. **Source Image Ground-Truth Re-Check**: Crucially, no text is ever edited on an LM's confidence alone. Any surviving anomaly triggers a targeted vision check against the cropped source PDF page image, ensuring a fix is only applied if verified by ground truth.

Running the tool against the motivating file succeeded immediately: it caught the radical symbol failure and correctly repaired page 6 to read `$$\sqrt{h^2 + k^2}$$`, while independently evaluating nine other flagged candidates and correctly leaving all nine untouched. 

Testing the pipeline at full corpus scale — across multiple documents including a 155-page lecture note file — surfaced two important insights about applying general NLP models to academic math:
- **Upstream Word Spacing**: Dozens of math terms were initially flagged as anomalous because LaTeX kerning offsets had glued words directly to variables ("LetVbe"). Fixing the upstream extractor to inject synthetic spaces for kerning offsets dramatically improved downstream precision.
- **Mathematical Vocabulary Calibration**: Terse mathematical prose ("subject to", "compact", "closed", "explicitly") naturally registers as statistically unusual (high surprisal) to general-purpose language models trained on standard web corpora. Empirical score distribution analysis established that while no single cutoff eliminates all false positives, calibrated threshold tuning reduced false-positive flags by 62% without losing sensitivity to corrupt glyphs. Because every change requires visual verification against the PDF image, false positives cost only a fraction of a cent in verification calls rather than risking text corruption.

Part of **Academic Hub**, acting as the downstream quality assurance safeguard for **[Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/)** and ensuring clean context reaches **[Source Indexer](/projects/academic-hub/source_indexer/)**.
