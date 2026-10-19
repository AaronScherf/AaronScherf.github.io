---
title: Video Lecture Notes
date: 2026-09-06
lastmod: 2026-10-16
summary: "Turn lecture videos into searchable study notes, while keeping the limits of grouping, coverage, and timestamp references visible."
type: academic-hub-project
image:
  caption: "Illustration: Combine related lectures without losing track of what needs checking."
  alt_text: "Lecture recordings feed transcripts and a combined study note, with a reminder that precise concept-to-video references are unfinished."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/pipelines/generate_video_notes
  - type: site
    icon: brands/github
    label: 'Status: Video Lecture Notes'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/generate_video_notes/2026-09-06-video-lecture-notes-status.md
tags:
  - Python
  - LLM / RAG
  - Hugging Face
params:
  subproject:
    id: generate_video_notes
    package: pipelines/generate_video_notes
    code_paths:
      - ai-sandbox/academic-rag-model/pipelines/generate_video_notes
    readme_path: ai-sandbox/academic-rag-model/pipelines/generate_video_notes/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/generate_video_notes/2026-09-06-video-lecture-notes-status.md
        role: current
        lifecycle_ids:
          - video-notes
    members: []
---

A lecture series can contain several explanations of the same idea, spread across videos with unhelpful titles. Video Lecture Notes downloads the audio, transcribes it, and combines related lectures into study notes that can be searched alongside textbooks and handwritten notes. The combination step matters: it tries to turn a sequence of recordings into one explanation rather than leave a separate transcript for every file.

<!--more-->

One trial exposed a surprisingly basic limit. A three-video group produced a note reflecting only one video's content because the local model was receiving only the end of the combined transcript. The shared model helper now requests enough context for the prompt. Rechecking showed better coverage and structure, although reliable links from each concept to the exact video moment remain unfinished.

## From recording to study note

Audio download, speech transcription, and note synthesis run locally. The transcript retains timed segments; the synthesis model receives them when drafting the combined note. Registering that note with the [Source Indexer](/projects/academic-hub/source_indexer/) uses the existing classification and embedding API calls, so the full searchable workflow is not entirely offline.

Grouping first uses playlist context and recognizable lecture-series titles. When that context is insufficient, it can compare transcript contents. This saves manual sorting, but shared vocabulary is not the same as belonging to the same lecture: the recorded trial grouped some differently numbered videos together and split another lecture's two parts.

For an **illustrative output**, a note might organize "Sets and functions" into definitions, examples, and a comparison of related ideas. That describes the intended format, not an excerpt from the recorded run. To check an explanation, I still need the recordings and transcripts; a general video link at the end is less useful than a precise reference beside the claim.

## What the trial covered

The September 2026 record covers eight videos from a 105-video Math Camp playlist, across two passes. They produced five indexed notes. That establishes a working download-to-note path on a subset, not full-playlist coverage or complete retention of every explanation.

Long groups remain expensive to synthesize on CPU hardware, and the remaining timestamp and grouping issues affect practical review. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/generate_video_notes/README.md) and linked status record distinguish the implemented workflow from those open checks.
