---
title: Research Notes Conversion
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
  - Vector Database
---

A lightweight `.docx`-to-Markdown converter for PhD-application essays and loose research notes, proving the **[Source Indexer](/projects/academic-hub/source_indexer/)**'s design generalizes well past the one corpus it was originally built for — paired with **[Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/)** as one of the two source corpora feeding **AI Research Assistant**.

<!--more-->

Unlike the PDF pipelines this project started with, a `.docx` already carries its own structure — headings, bold/italic runs, lists — in the file format itself, so there's no OCR problem to solve and no GPU needed: `mammoth` reads that structure directly into Markdown, entirely locally. The one real wrinkle was cosmetic but corpus-wide: `mammoth`'s writer defensively backslash-escapes ordinary punctuation everywhere in the text, not just where it would actually be ambiguous, so "well-known" and "the U.S." came out as `well\-known`/`U\.S\.` across every converted file. Confirmed safe to invert unconditionally — none of the essays have a real paragraph starting with a literal `1.` or `-`, the one case the escaping exists to protect against — and reversing it was a five-line regex, not a rewrite.

Wiring this corpus into the existing indexer turned out to need almost no new code, because the indexer's core functions were never actually hardcoded to Academic Hub's own folder — `reconcile_and_write()` just takes a root path as a parameter. The only two real gaps, both found by actually running it rather than guessing in advance: a `tags: []` frontmatter line had to be added to match the notes pipeline's own convention, since the tag-mining pass patches that line in place and silently skips any file that doesn't already have one; and the document-type classifier's prompt turned out to be hard-coded to Academic Hub's own four-value vocabulary (`textbook`, `problem_set`, `ta_notes`, `handwritten_notes`) — every one of 19 real essay and research-note files got force-fit into `textbook` or `handwritten_notes`, neither of which is remotely correct for a personal statement of purpose. Making that vocabulary a parameter instead of a constant fixed it project-wide with zero effect on Academic Hub's own existing behavior, and a full re-index against the real corpus afterward correctly classified every file as `personal_essay` or `research_notes`.

Getting this corpus to actually *talk to* Academic Hub, not just sit next to it, meant generalizing the query side to search more than one root at once — `search`, `search_passages`, and the tutoring agent now take a list of corpus roots instead of a single path, mirroring a `--root`/repeatable-flag convention already proven out elsewhere in the same codebase. The one real design subtlety: two unrelated corpora can each have a course literally called `notes`, so a candidate result has to be tracked as a `(root, course)` pair, not a bare course name, or a query spanning both would risk reading the wrong shard entirely. Confirmed live with two genuinely different questions against both corpora in one call: a linear-algebra query correctly surfaced only Academic Hub results, and a "PhD statement of purpose" query correctly surfaced only this corpus's — real topic-based federation, not one root silently winning by default.

The last gap only showed up once the tutoring agent was actually asked a real question: every citation came back with an empty label. The chunker's page-based fallback tier was built for the PDF pipelines' `<!-- page N -->` markers, and a `.docx` has no such thing — it was silently producing one giant "page" span with no page number to cite at all. A genuine paragraph tier now fills that gap, numbering paragraphs directly so a citation reads like `¶4` or `¶6-8` — a locator that actually means something for a one-or-two-page essay, unlike a page number it was never going to have. Heading-tier citations still take priority when a document has real structure (a couple of the research-notes files with actual bullet organization got those instead); paragraph is specifically the last-resort fallback, not a length-based rule. Re-running the exact same tutoring question after the fix produced well-formed citations across the board, on the same real 19-file corpus that had motivated finding the bug in the first place.

This is still growing, not finished: today it's a fixed local folder, hand-run rather than watching a live source. The plan is to pull loose-form research-idea essays directly from Google Drive instead of a manually-populated folder, and to fold in a proper literature-review workflow once there are enough papers indexed to make one worth building. The document-type vocabulary is already built to be extended per corpus rather than shared, so whatever comes next slots in the same way `personal_essay` already did, with no changes needed to the retrieval layer underneath. Part of the same **[Source Indexer](/projects/academic-hub/source_indexer/)** / **[RAG Analysis](/projects/academic-hub/rag_analysis/)** ecosystem this builds directly on top of.
