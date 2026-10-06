---
title: Tidying Up Academic Hub's Plumbing
summary: "Two behind-the-scenes changes make the academic resource library easier to sync and the software easier to navigate."
date: 2026-10-03
authors:
  - me
tags:
  - Academic Hub
  - Python
image:
  caption: 'A lightweight notes library and a better organized academic resource toolkit'
  image_suggestion: "Two-panel diagram showing a lightweight notes collection syncing separately from large reference files, and software components grouped by their roles."
---

Not every useful improvement adds a visible feature. Some make the tools easier to maintain or keep the notes workflow responsive.

<!--more-->

I separated large reference files from the handwritten notes that need to sync between devices. The tablet now syncs the working notes and drawings without carrying the full archive along with them.

I also reorganized the Academic Hub code so related tools sit together by what they do. This makes it easier to see how document conversion, discovery, shared utilities, and tutoring fit into the larger project.

The codebase change was a mechanical reorganization, with no intended change to tool behavior. The full automated test suite passed after the move. The [Obsidian sync page](/projects/academic-hub/obsidian_git_sync/) and related project pages describe the technical details and ongoing maintenance.
