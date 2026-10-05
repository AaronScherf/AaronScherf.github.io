---
title: "Ditching OneNote and GoodNotes: Why Obsidian, Excalidraw, and Git Win for Academic Notes"
summary: "Why proprietary tablet note apps fail graduate students in mathematics and economics, how plain-text .excalidraw.md files enable true Git version control, how I hacked the tablet interface with custom JavaScript and CSS, and how splitting repositories keeps mobile sync fast while feeding downstream AI models."
date: 2026-09-24
authors:
  - me
tags:
  - Academic Hub
  - Git
  - JavaScript
  - LLM / RAG
  - Productivity
image:
  caption: 'Obsidian + Excalidraw handwritten math note workflow with custom stylus tooling, lightweight Fit GitHub API sync, and downstream AI transcription'
  image_suggestion: "Comparison diagram contrasting proprietary note apps with an Obsidian + Excalidraw + Git workflow: showing tablet drawing on an infinite canvas, bundled JS customization for eraser/stylus tools, CSS gesture adjustments, lightweight Fit GitHub API sync to academic_notes/ (<50MB) isolated from academic_resources/, and downstream AI transcription to LaTeX Markdown."
---

If you study mathematics, statistics, or economics at the graduate level, a keyboard alone is rarely enough. You cannot comfortably type live matrix transformations, commutative diagrams, game-theoretic game trees, or dynamic optimization phase diagrams at the speed a professor writes them on a chalkboard. A stylus and a tablet are essential.

<!--more-->

*Figure: Obsidian + Excalidraw handwritten math note workflow with custom stylus tooling, lightweight Fit GitHub API sync, and downstream AI transcription.*

For years, the default advice for students has been to pick up an iPad or Android tablet and download Microsoft OneNote, GoodNotes, or Notability. On the surface, these apps seem fine: they have smooth ink, highlighters, and cloud sync. But as your coursework expands across semesters into hundreds of pages of derivations, their foundational flaws become impossible to ignore.

Here is why I walked away from proprietary tablet note apps, how I built a hackable, Git-versioned handwriting workflow using **Obsidian** and **Excalidraw**, and how treating handwritten notes as plain text unlocked automated AI transcription and semantic retrieval across my entire academic vault.

---

### 1. The Hidden Costs of Proprietary Note Apps

The fundamental flaw of apps like OneNote, GoodNotes, and Notability is not their pen latency — it is **data lock-in**:

1. **Closed Binary Formats**: Your mathematical thoughts are trapped inside opaque SQLite databases or proprietary binary containers. If the app developer changes their pricing model, discontinues support, or deprecates export features, your years of intellectual work are held hostage.
2. **Fragile Version Control**: Proprietary apps offer no meaningful version control. There is no Git commit history, no branch workflow, no visual diffs, and no way to roll back a corrupted drawing without hoping an undo stack is still intact in memory.
3. **Silent Math Corruption**: This was the dealbreaker for me. When exporting or copying text from OneNote, its native OCR silently drops mathematical equation blocks entirely rather than flagging an error. Worse, its infinite canvas layout frequently breaks paragraphs across non-adjacent PDF pages, making automated downstream processing impossible.

---

### 2. The Obsidian + Excalidraw Breakthrough: Plain-Text Ink

The alternative is **Obsidian** paired with the **Excalidraw plugin**. 

Instead of storing drawings in a proprietary database, Excalidraw stores drawing elements (freehand paths, text blocks, geometric arrows, and math equations) as structured JSON embedded inside a standard `.excalidraw.md` Markdown file.

This simple design choice changes everything:
- **True Ownership**: Your notes are plain files residing on your local filesystem. They work completely offline, require zero subscription accounts, and will remain readable decades from now.
- **Git Versioning**: Because the files are Markdown and JSON, every lecture revision, annotation, or diagram edit can be tracked, branched, and committed with standard Git tooling.
- **Infinite Flexibility**: You can sketch live mathematical derivations, paste lecture slide PDFs directly alongside your handwritten annotations, and link concepts bidirectionally to other Markdown notes in your vault.

---

### 3. Hacking the Tablet Experience (JavaScript & CSS)

Running Obsidian on a tablet with an active stylus is powerful, but desktop-oriented plugins often suffer from rough ergonomics on mobile devices. Because Obsidian’s plugin architecture is built on open web standards (HTML, CSS, and JavaScript), I was able to customize the interface to match my exact needs.

#### Localizing the Stylus Menu & Building an Eraser
I discovered a community stylus floating toolbar that streamlined pen selection, but its interface and documentation were entirely in Russian. Rather than abandoning it, I opened the plugin’s bundled `main.js` on my laptop, translated the localization strings into English, and inspected its tool-switching handlers. 

Excalidraw exposes a clean internal `setActiveTool` API. By hooking directly into this API within `main.js`, I added a dedicated, toggleable eraser button directly onto the floating stylus menu — eliminating the need to reach across the screen to the primary toolbar while writing.

#### Resolving OS Gesture Clashes with CSS
On modern tablets, swiping up from the bottom edge triggers the operating system's app switcher or home gesture. In stock Excalidraw, the canvas zoom controls and undo/redo buttons sat directly above this bottom bezel, causing accidental gesture triggers during intense lectures.

By injecting a lightweight CSS snippet via `.fitattributes.json`, I adjusted the positioning of the canvas controls, shifting them up by `2rem`:
```css
/* Nudge Excalidraw canvas controls above tablet OS navigation bar */
.excalidraw .App-bottom-bar {
  margin-bottom: 2rem !important;
}
```
This simple override moved the interface completely out of the gesture zone, making the canvas completely reliable under hand pressure.

---

### 4. Architecting Mobile Git Sync Without History Bloat

The hardest engineering hurdle was keeping notes synchronized between my tablet and laptop.

Running a full Git client on mobile devices is notoriously fragile. Over several months, course PDFs and lecture recordings had drifted into my notes folder. As Git tracked these changes, it accumulated 87 large binary blobs totaling over 217MB. Every time the tablet attempted to run `git fetch`, the mobile Git client ran out of memory and crashed.

To resolve this, I implemented a two-part architectural overhaul:

#### Step 1: Deep History Pruning with `git-filter-repo`
Rather than merely adding files to `.gitignore` (which leaves old bloated blobs in Git history), I used `git-filter-repo` to rewrite the repository history, purging every historical PDF and video blob byte by byte. This pruned the repository from **217MB down to 35MB** with zero loss of notes or commit provenance.

#### Step 2: API-Based Sync via Fit
Instead of relying on a local Git engine on the tablet, I transitioned to **Fit**, an Obsidian plugin that synchronizes files by communicating directly with the GitHub API. It pushes and pulls only changed Markdown and drawing files, avoiding local object compilation entirely.

#### Step 3: Strict Repository Splitting
To ensure the vault stays permanently lightweight, I separated the file trees into two distinct repositories:
- `academic_notes/`: A private, lightweight Git repository (<50MB) containing exclusively Markdown notes, `.excalidraw.md` drawings, and embedded diagrams. This syncs to the tablet instantly on every app open.
- `academic_resources/`: An isolated storage directory housing gigabytes of source textbooks, raw problem set PDFs, and lecture video recordings, kept out of version control and backed up via Rclone.

---

### 5. From Handwritten Ink to Downstream AI

In OneNote or GoodNotes, handwritten ink is functionally dead data — it sits in an archive, rarely re-read and impossible for machine learning tools to parse.

In **Academic Hub**, handwritten notes are active inputs to a broader AI ecosystem:

1. **Automated Transcription**: The **[Notes Transcription Pipeline](/projects/academic-hub/notes_transcription/)** processes exported `.excalidraw.png` drawings and lecture notes, converting handwriting into structured Markdown with clean LaTeX math blocks.
2. **Font-Baseline Reconstruction**: Using `PyMuPDF`'s layout engine, the pipeline analyzes character bounding boxes and vertical baseline offsets, reconstructing lost superscripts ($x^2$, $D^5$) for free before routing complex equations to multimodal vision models.
3. **Dual-Canvas Deduplication**: During lectures, I often create two versions of a note: an ink-only canvas drawn live, and an "ink + slides" canvas where presentation slides are pasted alongside. To prevent both versions from clogging up search results in my RAG tutor, the **[Source Indexer](/projects/academic-hub/source_indexer/)** uses a 3-gram lexical containment metric (`core/indexer/related.py`) to automatically link the pair, collapsing them into a single primary card while keeping the raw handwritten version linked as a subset.

---

### Why This Matters

This workflow demonstrates that technical sovereignty and day-to-day usability do not have to be in conflict. By choosing open file formats over proprietary silos:
- You gain permanent, offline ownership of your intellectual work.
- You gain the full rigor of Git versioning and collaborative workflows.
- You turn everyday handwriting into machine-readable data that feeds directly into custom AI tutoring agents.

For students, educators, and software engineers alike, the lesson is clear: when your tools are built on open text and transparent protocols, you are never locked into what an app developer imagined — you can shape your tools to match how you actually think.
