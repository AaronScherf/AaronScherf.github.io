---
title: Academic Hub
date: 2026-09-01
lastmod: 2026-10-16
summary: "A study workspace connecting handwritten notes, textbooks, source-linked answers, and reviewed study materials."
image:
  caption: "Illustration: Follow a question from course material to a reviewed study aid."
  alt_text: "A course question moves through searchable text and a source-linked answer to a draft study guide, human review, and collection maintenance."
  focal_point: Center
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

A question in my handwritten notes can become the starting point for a textbook lookup, an explanation with source references, and a study guide. Academic Hub connects those steps by keeping converted materials searchable and preserving a route back to the originals. I choose which tools to run and review their outputs along the way.

<!--more-->

The common foundation is a collection of passages I can find and return to. Conversion preserves the text, mathematical notation, and page context; the [Source Indexer](/projects/academic-hub/source_indexer/) makes that material searchable. From there I can ask a question, develop a fuller study explanation, or explore how course concepts depend on one another. These are different ways to work with the same materials.

## Prepare the materials

- [Textbook conversion](/projects/academic-hub/marker_conversion/) preserves equations, figure descriptions, and page references; [notes transcription](/projects/academic-hub/notes_transcription/) handles shorter documents and handwriting.
- [Post-processing](/projects/academic-hub/postprocess_notes/) flags suspicious extracted text and compares it with source images before changing it.
- [Video Lecture Notes](/projects/academic-hub/video_notes/) turns lecture recordings into study notes. Reliable references from each concept back to its exact moment in a video remain unfinished.

## Find an explanation

[RAG Analysis](/projects/academic-hub/rag_analysis/) uses retrieved passages to answer a question with references I can open and check. I can save an answer or a session recap as a study note; [Summary Enhancement](/projects/academic-hub/summary_enhancement/) can return to its recorded passages to develop the explanation further.

[Concept Graph](/projects/academic-hub/concept_graph/) uses the shared source material to map relationships between ideas, including the assumptions that make a conclusion follow. Its first full graph covers part of a microeconomics course. A graph helps trace those dependencies; a guide explains a topic in sequence. Both contain drafted material that needs review.

## Study and practice

- [Study Guide Pipeline](/projects/academic-hub/study_guide_pipeline/) starts from a topic list, selects indexed sources, drafts a guide, and proposes edits for review. Its optional enhancement step adds the same fuller explanations and worked examples available to an existing summary.
- [Tutor Diagnosis](/projects/academic-hub/tutor_diagnosis/) gives hints and feedback on an attempt. The separate [Socratic Tutor](/projects/academic-hub/socratic_tutor/) tracks progress during a conversation, but its strict checks have struggled with teaching unfamiliar material.
- [Guided Solutions](/projects/academic-hub/guided_solutions/) keeps my reasoning, agent derivations, and tutoring work distinct for comparison.
- [Problem Corpus](/projects/academic-hub/problem_corpus/) stores extracted exercises with their provenance. [Problem Generation](/projects/academic-hub/problem_generation/) currently retrieves its own style examples; integration with that stored bank remains separate work.
- [Visualizations](/projects/academic-hub/visualization/) can accompany an explanation, while [Audio Generator](/projects/academic-hub/audio_generator/) turns notes into spoken episodes. A generated chart or recording still needs checking for its intended use.

## Maintain the collection

[Obsidian Git Sync](/projects/academic-hub/obsidian_git_sync/) keeps working notes available across devices. [Corpus Health](/projects/academic-hub/corpus_health/) reports missing or stale outputs for review, and [Project Steering](/projects/academic-hub/project_steering/) helps prioritize the next work.

The [subproject collection](/projects/academic-hub/) links to each tool's current evidence and limits. A useful study session still involves choosing the material, checking coverage, and comparing generated explanations with their sources. The shared source trail makes those checks possible; it does not settle whether an explanation is correct.
