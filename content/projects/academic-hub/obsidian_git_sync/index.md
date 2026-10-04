---
title: Obsidian Git Sync
date: 2026-09-21
type: academic-hub-project
image:
  caption: 'Obsidian tablet interface with Excalidraw stylus customization and lightweight Fit GitHub API sync'
  image_suggestion: "Screenshot of the Obsidian tablet interface displaying an Excalidraw handwritten lecture note with the customized, localized stylus popup menu and eraser tool, accompanied by an architectural diagram showing the lightweight Fit GitHub API sync between tablet and laptop with heavy PDFs isolated in academic_resources/."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-21-obsidian-git-sync-status.md
  - type: site
    icon: brands/github
    label: Follow-up notes
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-26-obsidian-git-sync-status.md
tags:
  - Git
  - JavaScript
---

Keeps handwritten Excalidraw lecture notes in sync between a tablet and a laptop through plain Obsidian + GitHub, with course PDFs and textbooks deliberately kept out of the loop so the tablet's git client never has to move more than a few megabytes of Markdown.

<!--more-->

*Figure: Obsidian tablet interface featuring Excalidraw handwritten lecture notes and localized stylus tools, synchronized via lightweight Fit GitHub API architecture.*

The objective is narrow on purpose: two Obsidian vaults, one on each device, agreeing on the same lightweight notes without either device ever downloading the gigabyte of source PDFs, textbooks, and lecture recordings that live alongside them in **Academic Hub**. `.excalidraw.md` notes, their embedded PNGs, and downstream processed Markdown should sync every time; anything heavy — PDFs, Office docs, and the auto-exported `.svg` renders of each drawing — should never leave the device it was created on. The approach so far is a repo split, not a single vault: `academic_notes/` was carved out as its own standalone git repo (private, on GitHub) nested inside the main portfolio repo, which gitignores it entirely, so the two histories never entangle. `academic_resources/` — course textbooks and recordings — was already living as a sibling folder one level up with the same "heavy subpaths gitignored" pattern; the current work is finishing the job by relocating the PDFs that had drifted into `academic_notes/` over time into that existing home, rather than inventing a third structure.

Enforcing the size boundary turned out to be the hard part, not the repo split itself. The tablet's sync plugin regenerates `.gitignore` from its own local settings on every app launch — on *either* device, independently — which means a rule added on the laptop silently vanishes the next time the tablet opens, and vice versa; the file in git is a snapshot of whichever device loaded last, never a stable source of truth. That mechanism produced a real incident: PDFs slipped past a blanked-out ignore rule, got committed on a routine auto-backup, and the accumulated history — 87 large blobs across the repo's life, 184MB or so — was enough to reliably crash the tablet's git client trying to fetch it. The fix used `git-filter-repo` to strip those blobs from every commit rather than just the current snapshot (217MB → 35MB), which meant force-pushing rewritten history and re-verifying, file by file and byte by byte, that nothing legitimate got caught in the cleanup — a discipline worth keeping for the resources/notes split still ahead, since a bulk file move deserves the same path-by-path, hash-by-hash check before it's trusted.

The other half of the approach was managing a tablet-only plugin from the laptop instead of the device it runs on. A custom Excalidraw stylus menu — originally documented only in Russian — got fully localized and gained a new eraser button (calling Excalidraw's own `setActiveTool` API rather than simulating a click on its toolbar) by editing the plugin's bundled `main.js` directly on the laptop. The same repo-splitting logic was extended to Obsidian's own plugin-enable list, previously a single shared file that had already caused one merge conflict — each device now keeps its own enabled-plugin set locally.

The tablet's sync plugin was later swapped again, this time from Direct Git Sync to **Fit**, which talks to the GitHub API directly instead of driving a local git clone — sidestepping the history-bloat crash class above entirely. It came with its own hard rule, though: Fit refuses, unconditionally, to ever write `main.js`/`manifest.json`/`styles.css` inside any plugin folder, on the theory that a plugin's code belongs to Obsidian's own plugin manager, not to a sync tool. That's a deliberate, permanent design choice, not a bug to work around — so the stylus-menu localization above no longer reaches the tablet through git sync at all; it's now a manual one-time file copy whenever that plugin's code changes. CSS, by contrast, isn't covered by that rule: a snippet nudging Excalidraw's on-canvas zoom and undo/redo controls up a couple of rem — they'd been sitting right under the tablet's OS gesture bar, unpressable — syncs through Fit just fine once opted in via a small `.fitattributes.json` manifest, including riding out the "both sides added this new file at once" conflict Fit raises the first time any new path gets tracked that way.

Once synced notes land in the hub repository, they surfaced a subtle algorithmic challenge downstream in **[Source Indexer](/projects/academic-hub/source_indexer/)**: dual-canvas duplication. In practice, a lecture often produces two distinct Excalidraw canvases — an original handwriting-only file drawn live in class, and a second "with slides" canvas created later where PDF lecture slides are pasted alongside the original ink. Both versions are transcribed to Markdown and preserved on disk, but indexing both cards independently polluted the retrieval space: because the slides note is a strict superset of the handwriting note, search results returned both near-identical documents in top-k slots, crowding out textbook passages and other lectures for both the RAG tutor and the problem generator.

Attempting to deduplicate or pair them using card embeddings failed completely: across a live microeconomics lecture series, card embedding cosine similarity between a handwriting note and its slide superset was 0.879–0.920, but unrelated lectures in the same course scored up to 0.897 — dense topical similarity made dense vector embeddings blind to whether two documents were duplicate versions or different lectures on the same economic concepts. The solution was a specialized lexical metric in `core/indexer/related.py`: isolating only the `**[Handwritten]**` blocks in the superset and calculating word 3-gram containment of the subset's vocabulary. That metric separated true pairs (0.59 to 0.83) from non-pairs (0.00 to 0.02) with zero overlap, allowing a calibrated 0.30 threshold to automatically link them. The subset card records `subset_of: <superset_file_id>`, allowing default search queries to cleanly collapse the pair into the comprehensive superset while keeping the standalone handwriting note accessible via `--include-subsets` when requested.

Next up: actually relocating the PDFs and SVGs into `academic_resources/`, updating the scripts in the Academic Hub pipeline that currently read course material straight out of `academic_notes/`, and tightening the ignore-rule mechanism on both devices so it's harder to silently break the way it did this round.
