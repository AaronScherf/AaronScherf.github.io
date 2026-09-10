---
title: Audio Generator
date: 2026-09-09
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/audio_generator
tags:
  - Python
  - LLM / RAG
---

Converts a course's Markdown notes and converted textbooks into local MP3 narration for commute and exercise listening — discovery, cleaning, and TTS synthesis all run offline on CPU, with one narrow exception: turning dense LaTeX into speakable prose is handed to a tiered Gemini API call, the one step regex and a local model both proved unequal to.

<!--more-->

For each discovered `.md` file — a student's own notes under `academic_notes/<course>/`, or a converted textbook under `academic_resources/<course>/.../processed_outputs/` — the pipeline strips code blocks and markdown syntax, converts LaTeX into narration-ready prose, synthesizes speech via Piper (fast, default) or Kokoro-ONNX (slower, higher quality), and writes the resulting MP3 as a sibling of the source file, in the same hub content repo a student's own sync tooling already watches. A SHA-256 content hash keyed to each source path means a re-run only regenerates audio for files that actually changed. The dense per-sentence timestamp citations **[Video Lecture Notes](/projects/academic-hub/video_notes/)** attaches to its synthesized notes are stripped before narration too, since a citation is only useful as a clickable link, not read aloud.

The one step that isn't free is turning raw LaTeX into something a TTS voice can actually read. The original regex wrap (`Equation: <raw LaTeX>`) passed literal, unpronounceable command syntax straight through once tested against a real equation-dense note, so narration moved to an LLM. A local `qwen2-math:7b` model fixed the correctness problem but, measured end-to-end against a real 121,637-character file, took roughly six hours to narrate one document — not usable at any real batch volume. Replacing it with the Gemini API cut that to 13 minutes for the same file, about 28x faster, by classifying each chunk's LaTeX density before sending it anywhere: no-math chunks make zero API calls, sparse notation goes to a cheap model, genuinely dense equations go to a stronger one — and every chunk is dispatched through a thread pool rather than a serial loop, since the API, unlike a single local model, serves concurrent requests fine.

Running that pipeline end-to-end against the same real file surfaced a second, unrelated problem: one technically-correct MP3, 3 hours 22 minutes long — accurate, but useless for a commute. A section-aware splitting pass now breaks a long note at every Markdown header, narrates and cleans each section, then greedily groups consecutive sections into 10-20 minute episodes using a real measured calibration (969 characters of narrated text per minute of Piper audio, from one real run) rather than a guessed speaking rate. The first working version of this grouping made a real concurrency mistake worth naming: narrating one section at a time, in a loop, confined each section's own parallelism to its own serialized batch — flattening every section's chunks into one shared dispatch before narrating anything fixed it, cutting narration time for a 74-section file from 13 minutes down to under 4.

The full real-world run — the same 121,637-character TA notes file, now split into 9 episodes — took 3.8 minutes to narrate and 19.4 minutes to synthesize across 3 concurrent Piper workers (a 2.9x speedup over doing it sequentially), 23.2 minutes total end-to-end for nine separately listenable files instead of one unplayable-length one. It also confirmed a known limitation rather than papering over it: one 711-line, header-less section came out as its own 62-minute episode, since the design deliberately never splits inside a single section — left unfixed, on purpose, pending a listening-quality pass on the real output first. Worth being honest about what this test actually exercised, too: raw, unedited LaTeX-heavy notes are the pipeline's hardest case, not its main one — the intended primary use is narrating already-plain-prose LLM-generated summaries, which wouldn't need the Gemini narration step at all. That summary pipeline doesn't exist yet.

Part of **Academic Hub**, reusing the same `common/gemini_utils.py` client already shared by **[Source Indexer](/projects/academic-hub/source_indexer/)** and **[Visualization Sub-Agent](/projects/academic-hub/visualization/)**, and stripping the same per-sentence timestamp citations **[Video Lecture Notes](/projects/academic-hub/video_notes/)** attaches to its synthesized notes.
