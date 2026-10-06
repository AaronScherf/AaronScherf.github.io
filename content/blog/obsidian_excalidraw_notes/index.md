---
title: "Why I Use Obsidian and Excalidraw for Academic Notes"
summary: "A look at how linked notes, handwritten diagrams, and an existing academic resource library work together, along with the tradeoffs that remain."
date: 2026-09-24
authors:
  - me
tags:
  - Academic Hub
  - Productivity
image:
  caption: 'Handwritten academic notes connected to a searchable library of course resources'
  image_suggestion: "Diagram showing a tablet note linked into a larger searchable academic library, with a visible SVG export step for handwriting transcription."
---

I take many of my academic notes by hand. Diagrams, equations, and quick annotations are often easier to draw than type, but handwritten pages are hard to search and connect to related material later.

<!--more-->

I use **Obsidian** and **Excalidraw** to keep handwritten notes alongside a larger collection of course materials. The main benefit is not just owning the files: Obsidian's linked-note structure fits the way I already organize and index academic resources. A note can point to related concepts and material, and the broader collection can be searched together.

OneNote and GoodNotes made writing feel natural, but their file-type limits got in the way of my processing workflow. Excalidraw is more flexible for my notes, though it is not a one-click solution: I still export drawings as SVG files before the handwriting transcription process can use them.

The setup also has practical tradeoffs. I adjusted the tablet interface to make common pen tools easier to reach and moved controls away from the operating-system gesture area. To keep tablet syncing manageable, I use an API-based sync plugin and keep large reference files out of the notes sync. That arrangement takes maintenance, and plugin settings or code do not always sync automatically.

Once exported, the handwritten notes can be transcribed and added to the same searchable library as other academic material. The indexer can also identify some closely related versions of a note, such as a handwritten page and a copy that includes lecture slides. That matching is still being refined, so it should be treated as a helpful connection rather than perfect automatic organization.

The result is a workflow that connects handwriting to the rest of my academic materials, while leaving the original notes editable. It involves an export step and some setup, but the links between notes and resources make it more useful to me than a collection of isolated pages.

For the sync setup, transcription steps, and current matching limits, see the [Obsidian and Git Sync](/projects/academic-hub/obsidian_git_sync/), [Notes Transcription](/projects/academic-hub/notes_transcription/), and [Source Indexer](/projects/academic-hub/source_indexer/) project pages.
