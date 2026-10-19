---
title: "Giving the Questions in My Lecture Notes Somewhere to Go"
summary: "Handwritten questions can lead to saved explanations, with a visible distinction between answers drawn from course materials and answers that still need sources."
date: 2026-10-04
lastmod: 2026-10-19
draft: false
image:
  caption: "Illustration: an answer can be worth exploring while still needing a course source."
  alt_text: "An illustrative handwritten margin question leads to two possible saved-answer outcomes: one has a course source, while a general explanation still needs source checking."
  focal_point: Center
authors:
  - me
tags:
  - Academic Hub
  - Learning Tools
---

A question in the margin of a lecture note can be the most useful thing on the page—and one of the easiest things to forget. The new question resolver gives those questions a follow-up: it finds the marked questions in transcribed handwriting, searches the course collection, and saves an explanation beside the note. Its first recorded run answered seven questions, with a useful distinction: four had supporting course passages and three did not.

<!--more-->

This builds on the handwritten workflow I described in my [Obsidian and Excalidraw post](/blog/obsidian_excalidraw_notes/). Excalidraw automatically saves an SVG image when I save a drawing. The [transcriber](/projects/academic-hub/notes_transcription/) makes the handwriting searchable and marks questions it finds. The resolver is a separate command at this milestone; saving a drawing does not automatically answer everything written on it.

Searching for an answer raises an awkward possibility: the system might find the question itself and treat that as evidence. The resolver excludes the note's own files when looking for supporting passages. If nothing suitable remains, it can still offer a general explanation, but labels it as not sourced from the course. That label describes the evidence available to the tool; it does not certify the other answers as correct.

Keeping the explanation beside the note matters too. The expanded transcript can be regenerated as the transcription tools improve. Pasting an answer into that generated text would put it at risk of disappearing on the next run. Instead, each question gets an identity, its answer lives in a companion file, and the note carries a link back to it. The original question remains available for comparison.

The first live run covered four microeconomics notes. All seven answers were saved, and file-level search could find the companion files afterward. One spot-checked explanation correctly distinguished a necessary condition from a sufficient one and pointed to the relevant course material. The three answers without course backing stayed visibly labelled. Passage-level search still needed a separate chunking step, so this was not yet a fully connected search workflow.

That last gap is a useful reminder of how the pieces fit together. Transcription makes the question readable; the [indexer](/projects/academic-hub/source_indexer/) makes related material findable; the answering tool connects them. Keeping the source trail visible lets me decide which explanation to pursue, which to check, and where the collection itself is missing something.

*Retrospective account prepared October 16, 2026, covering the milestone recorded October 4. Implementation began October 3; the [October 4 status revision](https://github.com/AaronScherf/ai-sandbox-master/blob/662696bf96f0519a2140e00c328d6b0049acf7e6/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-10-03-question-resolver-status.md) records the live run. The transcription and indexer project pages describe later work too.*
