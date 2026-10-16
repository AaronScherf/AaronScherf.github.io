---
title: Tidying Up Academic Hub's Plumbing
summary: "Keeping textbooks out of tablet sync and grouping related software tools make Academic Hub easier to maintain."
date: 2026-10-03
lastmod: 2026-10-15
authors:
  - me
tags:
  - Academic Hub
  - Python
image:
  caption: 'A lightweight notes library and a better organized academic resource toolkit'
---

Two recent changes to Academic Hub were about making the everyday work easier: keeping notes in sync and finding my way around the software.

<!--more-->

I separated large reference files from the handwritten notes that need to sync between devices. Before that, PDFs had slipped into the notes' saved history, so downloading the notes also brought along old copies of large files. The cleanup removed those files from the history, and the source documents moved to a separate archive. The tablet now syncs the working notes and drawings without carrying that archive along with them.

I also grouped the software tools by what they do: converting documents, finding papers, helping with study, or providing functions the other tools share. That gives me a clearer place to look when I need to change something.

The reorganization was intended to preserve how the tools work. The full automated test suite passed after the move. The [Obsidian sync page](/projects/academic-hub/obsidian_git_sync/) describes the sync setup, and the [Academic Hub overview](/projects/academic-hub-overview/) shows how the tools fit together.
