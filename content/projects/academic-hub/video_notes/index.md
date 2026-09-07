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

Run for real, in two passes, against a live 105-video Math Camp lecture playlist (8 videos total so far), the pipeline surfaced two real bugs worth documenting. The first: the shared **[Source Indexer](/projects/academic-hub/source_indexer/)**'s own classifier prompt only ever lets an LLM pick a `doc_type` from the fixed vocabulary it's handed, so every synthesized lecture note was silently filed as `handwritten_notes` — the closest of the four existing types — rather than falling back to its own folder name the way the original design assumed. A dedicated `doc_type` vocabulary for lecture notes, threaded through both places a note gets indexed, fixed it for good, verified against all five real cards produced so far. The second was more consequential and touched shared infrastructure: a 3-video group's synthesized note came back reflecting only one video's content, traced to Ollama silently defaulting to roughly 2,048 tokens of context whenever a caller doesn't request more — confirmed directly against the raw API (`prompt_eval_count: 2050` for a real ~22,000-token prompt) — and llama.cpp keeps the *tail* of an overflowing prompt, not the head. That single mechanism also explained an earlier, wrongly-diagnosed finding from the first pass: three different local models had appeared to categorically refuse to cite timestamps in their output, which looked like a model instruction-following ceiling but was actually the citation instructions (which sit at the top of every prompt) being silently truncated away before the model ever saw them. The fix — sizing Ollama's context window to the actual prompt automatically — lives in the shared Ollama helper both **[Visualization Sub-Agent](/projects/academic-hub/visualization/)** and **[Problem Generation Sub-Agent](/projects/academic-hub/problem_generation/)** also call, so both were quietly exposed to the same risk and now benefit from the same fix.

Re-verifying after that fix confirmed most of the damage was the truncation bug — content coverage and structure improved dramatically — but a smaller citation gap remains even now: the model acknowledges the timestamp-link mechanism exists but still tacks on one generic link at the end rather than citing inline per concept as asked. Next up: close that remaining citation gap (either a more directive, example-driven prompt or inserting citations programmatically after generation), empirically tune the content-clustering similarity threshold against a real case where it grouped videos in a genuinely surprising way, regenerate the handful of already-published notes now that synthesis quality has improved, and validate the pipeline against a full real playlist rather than a hand-picked subset — a large multi-video group's prompt turned out to be expensive enough on CPU-only hardware that it may need a summarize-then-combine approach rather than one giant concatenated prompt.

Part of **Academic Hub**, reusing **[Source Indexer](/projects/academic-hub/source_indexer/)**'s existing `doc_type`-based classification and card reconciliation unchanged, and following the same local-Ollama-only constraint already validated by **[Visualization Sub-Agent](/projects/academic-hub/visualization/)** and **[Problem Generation Sub-Agent](/projects/academic-hub/problem_generation/)**.
