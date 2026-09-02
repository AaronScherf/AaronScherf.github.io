---
title: Journal Article Transcription
date: 2026-09-01
type: ai-research-assistant-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model
tags:
  - Python
  - LLM / RAG
---

A PDF pipeline for academic journal articles that turned out to need almost no new code at all, reusing the **[Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/)**'s tiered cost-routing wholesale — paired with **[Research Notes Conversion](/projects/ai-research-assistant/research_notes_conversion/)** as one of the two source corpora feeding **AI Research Assistant**.

<!--more-->

Journal articles turned out to be the easy half: `notes/transcribe_notes.py`'s existing tiered pipeline — free local extraction where the text layer is clean, hybrid repair, full vision transcription as the fallback — already did exactly what a short academic PDF needs, so the new converter just calls its `process_pdf()` unchanged, pointed at a different, recursively-walked folder (journal articles live under thematic subfolders that may nest further, unlike academic-hub's flat per-category PDF folders) with its own `journal_article` document type.

One real, generalizable gap surfaced immediately: two of the first three real papers came from academic-publisher renderers (Apache FOP, XEP) the pagination-reliability check had never seen, routing genuinely clean PDFs to expensive page-by-page transcription for no reason — a two-line fix that benefits the notes pipeline too, not just this corpus. A user correction shaped the other real design decision here: the corpus had briefly held a 402-page monograph alongside genuine ~20-page papers, so anything over a page-count threshold is now flagged and skipped outright, never auto-escalated to the GPU/Marker pipeline — that stays reserved for files a human deliberately moves into Academic Hub's own folder, since it's the most expensive step in the whole project.

Not every finding closed cleanly. `page_looks_defective()`'s heuristics, tuned against LaTeX-typeset math lecture notes, flag a real, substantial fraction of pages in every one of the four real papers tested (32–43%) — enough to push all of them into whole-document Gemini batching instead of the cheaper hybrid-repair tier. Likely candidates are citation, footnote, and DOI conventions this checker has never seen. Left as-is: whole-document batching is still correct and still cheap (~$0.02/paper at measured per-page rates), and retuning defect detection for academic-paper prose specifically is a separable question from getting journal articles into the corpus at all. Similarly untouched: no live transcription-quality comparison against a dedicated OCR provider (Mathpix, Mistral) has ever been run, so the conclusion that Gemini is cheaper here is pricing-based only, not empirical accuracy.

Run for real: three distinct papers converted and indexed (a fourth turned out to be a byte-identical duplicate under a different filename, correctly deduplicated by the indexer's own content-hash identity, not a new bug), and a live query for "large language models applications" correctly surfaced both real papers on that topic — federated in the same result set as the essay corpus, no separate query needed. Part of the same **[Source Indexer](/projects/academic-hub/source_indexer/)** / **[RAG Analysis](/projects/academic-hub/rag_analysis/)** ecosystem this builds directly on top of, and reusing **[Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/)**'s own conversion machinery wholesale rather than duplicating it.
