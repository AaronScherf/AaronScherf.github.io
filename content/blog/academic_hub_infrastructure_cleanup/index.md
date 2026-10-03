---
title: Tidying Up Academic Hub's Plumbing
summary: Two housekeeping changes behind the scenes — splitting heavy course PDFs out of the synced notes vault so tablet sync stays fast, and reorganizing the entire pipeline codebase from flat subproject folders into role-based directories.
date: 2026-10-03
authors:
  - me
tags:
  - Academic Hub
  - Python
---

Most updates here are about a specific subproject shipping something new. This one is about the plumbing underneath all of them.

<!--more-->

**Splitting heavy files out of the synced notes vault.** `academic_notes/` is a private Obsidian vault, synced between a tablet and a laptop through [Fit](/projects/academic-hub/obsidian_git_sync/), a plugin that talks to the GitHub API directly instead of driving a local git client. That sync has to stay fast and small on a tablet, but over time PDFs and course recordings — things that get *read*, not edited — had drifted into the vault alongside the handwritten Excalidraw notes that actually need two-way sync. The fix was a repo split, not a bigger ignore list: `academic_resources/` now holds every textbook, recording, and course PDF as its own sibling location, and `academic_notes/` stays a lightweight vault of Markdown and embedded drawings only. The tablet's sync now never has to move more than a few megabytes on any given sync, no matter how many gigabytes of source material live alongside it.

**Reorganizing the pipeline codebase by role, not by history.** `academic-rag-model/` — the Python package behind all the PDF-to-Markdown conversion, indexing, and tutoring-agent work described on this site — had grown to about 15 flat, same-level folders (`notes/`, `essays/`, `rag/`, `viz/`, `indexer/`...), one per subproject, added in whatever order each one got built. That worked fine at five subprojects; at fifteen, the flat list stopped telling anyone — human or AI agent — how the pieces actually relate. Nothing in the directory tree said that `viz`, `problem_gen`, and `problem_corpus` all serve the tutoring agent, or that `essays`, `notes`, and `journal_articles` are all conversion pipelines sharing the same tiered-routing shape. The fix groups everything by role instead: `pipelines/` for the conversion tools, `discovery/` for finding source material, `agent/` for the tutor and its sub-agents, `core/` for the shared indexing and environment code everything else depends on — plus verb-first names (`convert_essays`, `transcribe_notes`) so a folder name states what it does, not just what it's about. It was a large enough mechanical change — about 15 packages, roughly 90 test files, and every doc cross-reference — that it ran through a full spec-and-review process rather than a quick rename pass, which paid off directly: a rigorous final review caught five silent path-resolution bugs that would have broken the exact CLI command this project's own setup notes tell an agent to run, none of them visible from the test suite alone.

Neither change touches what any of these tools actually do — just how cleanly the pieces are organized underneath them, which is the part that determines whether the next subproject is easy to add or one more thing to untangle.
