---
title: Indexing and Querying Academic Hub
summary: The two subprojects that turn converted Markdown into something queryable — Source Indexer and RAG Analysis — are both shipped and validated against the real corpus, closing the loop from raw PDF to a grounded, cited answer.
date: 2026-08-30
authors:
  - me
tags:
  - Academic Hub
  - LLM / RAG
  - Python
  - Vector Database
---

Since the last update, the two subprojects that turn a pile of converted Markdown into something actually queryable — **[Source Indexer](/projects/academic-hub/source_indexer/)** and **[RAG Analysis](/projects/academic-hub/rag_analysis/)** — have both gone from design sketches to real, validated systems running against the corpus.

<!--more-->

Four concrete pieces of progress:

- **Per-file index cards and corpus-wide tagging.** Every converted document now gets an index card keyed by a hash of its own source PDF (so it survives being moved or renamed), plus course-level rollups computed for free from existing card data. Deciding *what* to tag a file with took a real redesign: the original approach — graph clustering over file-embedding similarity — was tried against the real corpus and rejected outright, since no similarity threshold from 0.78 to 0.90 produced a clean subject split. It was replaced with a one-shot holistic tag proposal followed by per-candidate empirical validation, which is what's running today, with a fallback-tagging safety net (and a fix for that fallback leaking onto unrelated files) so no document goes untagged. Real corpus state: 30 healthy index cards, 0 orphaned, 0 untagged, a 14-tag vocabulary.
- **Passage-level retrieval, not just file-level.** Knowing *which document* is relevant to a query is a different, coarser problem than knowing *which paragraph* actually answers it — the file-level search shipped first is the cheap pre-filter, and passage-level chunking and embeddings now sit on top of it as the actual retrieval unit a tutoring agent grounds its answers in.
- **A grounded tutoring agent with real citations.** `rag_agent.py` answers a question using only retrieved passages, citing each one inline, and says so plainly when the retrieved material doesn't cover the question rather than filling the gap from general knowledge. Run for real, not just unit-tested: a live query — "what is the spectral theorem" — produced a substantive answer correctly synthesizing content from two different files at once, each citation a real, checkable theorem and page reference. A real side-by-side model comparison also reversed an earlier untested assumption: `gemini-3.6-flash`, originally picked on a "tutoring needs more reasoning" heuristic, showed no meaningful quality difference against the project's cheaper default tier once actually measured — so the cheaper model won.
- **Bugs that only showed up against the real, growing corpus.** A stale pre-rename filename in an exclusion list meant every index rebuild silently mis-treated the entire tag vocabulary, which would have let a pruning run delete it outright had it gone uncaught. Staleness detection based on file modification time turned out not to be a safe signal at all — a real rebuild once reported fourteen cards "updated" in a single run when nothing had actually changed, traced to something resetting every file's mtime at once — replaced with a content hash of the file's own bytes. And image-description metadata was writing a file link into its own sidecar state unconditionally, but only patching the index card if one already happened to exist at that exact moment, so the link silently never reached any of five real textbook cards despite the linked files existing on disk.

Full write-ups, including the specific corpus numbers and how each fix was validated, are on the **[Source Indexer](/projects/academic-hub/source_indexer/)** and **[RAG Analysis](/projects/academic-hub/rag_analysis/)** project pages. Together with Marker PDF Conversion and Notes Transcription, that's the whole Academic Hub pipeline working end to end now — raw PDFs in, a grounded, cited answer out — with persistent conversation memory and a problem-set subsystem next on the list.
