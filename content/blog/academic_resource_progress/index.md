---
title: Converting Academic Resources to Markdown
summary: An update on Marker PDF Conversion — chapter-aware chunking and page tracking for textbooks, automatic figure descriptions, a new GPU-free sibling tool for transcribing handwritten and typed academic notes, and a closer look at whether its output is actually clean enough for an LLM to read.
date: 2026-08-25
authors:
  - me
tags:
  - Academic Hub
  - LLM / RAG
  - Python
---

**[Marker PDF Conversion](/projects/academic-hub/marker_conversion/)**, the pipeline that turns raw academic PDFs into LLM-ready Markdown, has moved well past its original textbook-only scope since it was first introduced.

<!--more-->

Four concrete pieces of progress:

- **Chapter-aware chunking and page tracking.** The textbook pipeline used to split books into fixed 150-page chunks with no idea what was at the boundary — a cut could land mid-table or mid-formula. Chunk boundaries now align to real chapter breaks, and every page is tagged with both its physical PDF page number and the book's own printed page number, so an author's own "see page 157" can actually be resolved. Validated across four structurally different books with zero duplicate internal anchors and 96–98% page-number coverage.
- **Automatic figure descriptions.** A companion script now runs a cheap, GPU-free pass over already-converted books, describing each figure with Gemini and skipping decorative images for free. Along the way it caught a real, pre-existing bug — every image link in every previously converted book was silently broken — and fixed it. Across a five-book batch, 764 of 793 candidate images were described, with the rest correctly skipped as decorative.
- **A sibling tool for messier documents.** Textbooks are long but structured; problem sets, TA notes, and exams usually aren't — no table of contents, often short, and frequently mixing typed and handwritten content on the same page. A new local, GPU-free script handles these by routing each document to the cheapest tier its actual content supports: free local extraction when it's clean, targeted batched repair when only some pages are corrupted, and full vision-model transcription for handwritten or messy exports.
- **Making "free" local text actually trustworthy.** Two problems turned up on closer inspection: one text-extraction library was silently dropping spaces between words that another handled correctly (swapped for free, no downside found across ~1,150 real pages checked), and plain text can't represent a lost superscript at all (`D^5` reads as bare `D5`). The second problem turned out to be more fixable than it first looked: the same library's structured text mode exposes enough font-size and position data to reconstruct most lost exponents and subscripts locally, for free, instead of only detecting the loss and re-sending the whole document to Gemini — validated against real, already-correct transcriptions sitting on hand, with every case checked matching. One real gap stayed open along the way (a square-root sign that silently extracts as an ordinary letter, invisible to every check built so far, because it doesn't look wrong) — a finding that's steering the next phase toward a downstream correction pass rather than an ever-growing list of bespoke detection rules.

Full write-up, including the specific bugs found and how each approach was validated, is on the **[project page](/projects/academic-hub/marker_conversion/)**. Both tools now feed the same Academic Hub library, tagging their output with how it was produced so a downstream RAG pipeline can weight documents by provenance.
