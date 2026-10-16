---
title: Academic Hub
date: 2026-09-01
lastmod: 2026-10-16
summary: "A study workspace connecting handwritten notes, textbooks, source-linked answers, and reviewed study materials."
image:
  caption: "How source materials become searchable notes and study tools."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model
tags:
  - Python
  - LLM / RAG
params:
  subproject:
    id: academic_hub_overview
    package: null
    code_paths: []
    readme_path: null
    status_docs: []
    members:
      - source_indexer
      - transcribe_notes
      - convert_textbook
      - postprocess_notes
      - generate_video_notes
      - rag
      - tutor_diagnosis
      - socratic_tutor
      - visualization
      - problem_generation
      - problem_corpus
      - study_guide
      - summary_enhancement
      - audio_generator
      - corpus_health
      - project_steering
      - guided_solutions
      - obsidian_git_sync
      - concept_graph
---

A question in my handwritten notes can become the starting point for a textbook lookup, a checked explanation, and a study guide. Academic Hub connects those steps by keeping converted materials searchable and preserving references back to the sources. I choose which tools to run and review their outputs along the way.

<!--more-->

The useful connection is between a passage and what I do with it later. An answer can record which textbook sections it used; a guide can return to those passages for a fuller explanation. That source trail makes the work easier to inspect, even though a citation alone cannot establish that an explanation is correct.

[[Insert Image: Replace the dense architecture poster with four clear groups: "Prepare materials", "Find an explanation", "Study and practice", and "Maintain the collection". Follow one generic handwritten question through searchable text, a source-linked answer, and a reviewed guide. Show human review between outputs rather than implying a fully automatic learning system. Use large labels and invented content. Suggested caption: "Follow a question from course material to a reviewed study aid." Suggested alt text: "Notes and textbooks feed search, which supports answers and study materials with source references and human review." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

## Prepare the materials

- [Textbook conversion](/projects/academic-hub/marker_conversion/) preserves equations, figure descriptions, and page references; [notes transcription](/projects/academic-hub/notes_transcription/) handles shorter documents and handwriting.
- [Post-processing](/projects/academic-hub/postprocess_notes/) flags suspicious extracted text and compares it with source images before changing it.
- [Video Lecture Notes](/projects/academic-hub/video_notes/) turns lecture recordings into study notes. Reliable references from each concept back to its exact moment in a video remain unfinished.

## Find an explanation

[Source Indexer](/projects/academic-hub/source_indexer/) finds relevant documents and passages. [RAG Analysis](/projects/academic-hub/rag_analysis/) uses them to answer a question with references I can open and check. [Concept Graph](/projects/academic-hub/concept_graph/) offers another route through the material: connections between ideas, including the assumptions behind them. Its drafted explanations and connections still need review.

## Study and practice

- [Study Guide Pipeline](/projects/academic-hub/study_guide_pipeline/) selects sources, drafts a guide, and proposes edits for review. [Summary Enhancement](/projects/academic-hub/summary_enhancement/) develops a shorter summary into fuller explanations and examples.
- [Tutor Diagnosis](/projects/academic-hub/tutor_diagnosis/) gives hints and feedback on an attempt. The separate [Socratic Tutor](/projects/academic-hub/socratic_tutor/) tracks progress during a conversation, but its strict checks have struggled with teaching unfamiliar material.
- [Guided Solutions](/projects/academic-hub/guided_solutions/) keeps my reasoning, agent derivations, and tutoring work distinct for comparison.
- [Problem Corpus](/projects/academic-hub/problem_corpus/) stores extracted exercises with their provenance. [Problem Generation](/projects/academic-hub/problem_generation/) currently retrieves its own style examples; integration with that stored bank remains separate work.
- [Visualizations](/projects/academic-hub/visualization/) can accompany an explanation, while [Audio Generator](/projects/academic-hub/audio_generator/) turns notes into spoken episodes. A generated chart or recording still needs checking for its intended use.

## Maintain the collection

[Obsidian Git Sync](/projects/academic-hub/obsidian_git_sync/) keeps working notes available across devices. [Corpus Health](/projects/academic-hub/corpus_health/) reports missing or stale outputs for review, and [Project Steering](/projects/academic-hub/project_steering/) helps prioritize the next work.

The [subproject collection](/projects/academic-hub/) links to each tool's current evidence and limits. These range from fixture-tested rules to recorded runs on actual coursework; they do not all have the same degree of validation.
