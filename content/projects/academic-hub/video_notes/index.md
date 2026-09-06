---
title: Video Lecture Notes
date: 2026-09-06
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/video_notes
tags:
  - Python
  - LLM / RAG
  - Hugging Face
---

Turns a batch of YouTube lecture videos into synthesized Markdown notes indexed alongside the rest of the corpus — local audio download, local transcription, local Ollama synthesis, with no paid API call anywhere except the existing indexer's own per-document classification step.

<!--more-->

The pipeline runs entirely locally before a single Gemini call ever happens: `yt-dlp` resolves per-video and per-playlist metadata and downloads each video's audio track, `faster-whisper` transcribes it on CPU into timestamped segments, and once every video in a batch is transcribed, a fully automatic three-tier grouping algorithm decides which videos belong together as one logical lecture series before anything gets synthesized. Grouping was deliberately built with no manual per-batch configuration at all — a playlist is trusted as one coherent series by default, subdivided only when a title pattern (`Lecture N`, `Part N`, `Week N`) actually detects two or more distinct series bundled into the same playlist; videos with no playlist context fall back to clustering by transcript-embedding similarity (also local, via Ollama), then singleton groups for whatever's left. Synthesis is one local Ollama call per group, prompted with every member video's transcript tagged by its own per-segment timestamp link, so a note spanning multiple lectures can still point back to the exact video and moment a concept came from.

Run for real against the first eight videos of a live 105-video Math Camp lecture playlist, the pipeline surfaced one real indexing bug worth fixing: the shared **[Source Indexer](/projects/academic-hub/source_indexer/)**'s own classifier prompt only ever lets an LLM pick a `doc_type` from the fixed vocabulary it's handed, so a synthesized lecture note was silently filed as `handwritten_notes` — the closest of the four existing types — rather than falling back to its own folder name the way the original design assumed. A dedicated `doc_type` vocabulary for lecture notes, threaded through both places a note gets indexed, fixed it for good, with the real corpus cards re-verified afterward. A second finding is still open rather than fixed: three different local 7B Ollama models — a math-tuned one, a code-tuned one, and the general-purpose instruct default — all produced accurate, well-structured Markdown but consistently dropped every timestamp citation from the output, even with a 32K-token context window and no truncation in play. That rules out model size or context length as the cause; the working theory is that weaving literal URLs into freely generated prose is a harder ask for a small local model than the stylistic formatting it otherwise follows reliably, and the more promising fix is a redesigned prompt or programmatic citation insertion after the fact rather than a bigger model.

Part of **Academic Hub**, reusing **[Source Indexer](/projects/academic-hub/source_indexer/)**'s existing `doc_type`-based classification and card reconciliation unchanged, and following the same local-Ollama-only constraint already validated by **[Visualization Sub-Agent](/projects/academic-hub/visualization/)** and **[Problem Generation Sub-Agent](/projects/academic-hub/problem_generation/)**.
