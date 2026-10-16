---
title: Multi-Agent Development Workflow
date: 2026-09-27
lastmod: 2026-10-16
summary: "Coordinate AI-assisted work through explicit task handoffs, isolated working copies, and human-controlled integration."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/docs/AGENT_ROUTING.md
tags:
  - LLM / RAG
  - Developer Tools
image:
  caption: "Separate working copies feed one reviewed integration step."
---

For a website revision, I can give an agent the editorial guide and a set of pages, then review the resulting changes before publishing. That work happens in its own working copy, so another task can proceed without sharing the same files. The handoff carries the branch, changes, checks, and remaining questions.

<!--more-->

Git calls these separate working copies **worktrees**. Each writing task gets one branch and one writer; a designated integrator combines finished changes. The files and staging areas are separate, but Git's underlying history and branch references are shared. Isolation reduces accidental overwrites while leaving conflicts and incompatible changes for review.

[[Insert Image: Create a simple handoff diagram with two separate working copies, each labelled with a task, feeding a single "Review and integrate" point. Show a short handoff card containing "Changes", "Checks", and "Open questions". Keep publication behind a human decision. Use generic tasks rather than invented product interfaces or claims of shared agent memory. Suggested caption: "Separate the edits, then review how the changes fit together." Suggested alt text: "Two isolated task branches deliver handoff records to one human-controlled integration step." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

The workspace's routing guide assigns defaults by task. Claude handles architecture and decisions that depend on earlier context. Gemini handles pipeline operation, documentation, writing, and large source reviews. Codex handles routine code maintenance, tests, and Git mechanics. An explicit assignment can override those defaults—as it does when I ask Codex to revise these pages.

The routing instructions live in one shared document, linked from each agent's entry file. That avoids maintaining three copies that can drift apart. Continuity comes from the context and records supplied in this workspace; it should not be assumed to be automatic or shared between products.

A completed task still needs integration approval. Its handoff identifies what was changed, what was checked, and what remains uncertain. A passing test suite does not establish that two independently sensible changes will work well together.

This remains a convention the participants must follow. Worktrees do not isolate a shared notes vault, an external service, or a sync process. The [routing guide](https://github.com/AaronScherf/ai-sandbox-master/blob/main/docs/AGENT_ROUTING.md) and [worktree procedure](https://github.com/AaronScherf/ai-sandbox-master/blob/main/docs/WORKTREE_WORKFLOW.md) describe the boundaries and approval rules.
