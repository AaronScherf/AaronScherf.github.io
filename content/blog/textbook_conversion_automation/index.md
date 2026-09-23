---
title: Walking Away From the Textbook Conversion Pipeline
summary: Turning Marker PDF Conversion from a pipeline that needed a person watching every step into one that can run a whole batch unattended — a real corruption bug found and fixed at the root, duplicate detection that skips first and asks after, and a three-step automatic recovery ladder for out-of-memory failures.
date: 2026-09-22
authors:
  - me
tags:
  - Academic Hub
  - LLM / RAG
  - Python
  - Google Cloud Platform
---

**[Marker PDF Conversion](/projects/academic-hub/marker_conversion/)** has always done the actual conversion work unattended — spin up a GPU VM, convert every book in a course folder, tear the VM down. What it hasn't been able to do, until now, is run a *whole session* unattended: someone still had to sit through every duplicate-book prompt, every pre-run cost check, and manually intervene the moment a book turned out to be too large for the machine's memory.

<!--more-->

Three concrete pieces of progress, all aimed at that same goal:

- **A real corruption bug, found and fixed at the root, not just guarded against.** The pipeline's duplicate-book detection lets a book already converted for one course get reused for another instead of paying for a redundant multi-hour GPU conversion — but the mechanism it used to record that reuse turned out to collide with how the corpus-wide search index derives a book's identity. A plain index rebuild over a course holding one of these reused entries could silently evict the *original* course's own catalog entry from its own shard, confirmed live against real data. The stopgap at the time was a warning in the docs: don't run a rebuild near an affected course. The actual fix marks the reused entry with the identity of the book it's a copy of, and teaches the rebuild step to recognize that marker and skip past it instead of re-deriving an identity that collides with the original — covered by a new end-to-end test built specifically to fail without the fix, to make sure it stays fixed.
- **Duplicate detection that's biased toward the cheaper mistake.** Every uncertain duplicate match used to block the whole run on a person answering a prompt, which defeats the point of walking away. It's now split by confidence: a high-similarity match (above 0.85) is skipped immediately — no reconversion, no blocking — and logged to a small review queue instead of a live prompt, on the reasoning that the two possible mistakes aren't equally expensive. A book wrongly skipped only costs a follow-up conversion once someone notices; a real duplicate wrongly reconverted burns real, rented GPU time that's gone either way. Anything less certain still gets surfaced for an explicit yes or no, same as before.
- **Automatic recovery from out-of-memory failures.** A book too large for the VM's memory used to mean the whole batch stopped and waited for a person to notice, diagnose, and manually reset or resize the machine. It's now a three-step ladder: reset and retry on the same machine first, move up to a larger machine if the same book fails again on a fresh attempt, and only interrupt a person if the larger machine fails too — each step first checking the VM's own kernel log to confirm the failure was actually memory pressure, so an unrelated crash doesn't get misdiagnosed as OOM and burn through the ladder for nothing. Books are also now queued smallest-first, so if a resize does trigger, as little of the batch as possible is left running on a machine size decided under duress. Building this surfaced its own subtle bug before it ever shipped: recovering from a failure means wiping and relaunching, which was also wiping the exact evidence — the failure logs — that the *next* recovery step needed to know whether it had already tried the smaller machine. Fixed by having each step save what it needs to a small durable record on the VM itself before touching anything.

Full write-up, including the specific mechanism behind the corruption bug and the exact escalation thresholds, is on the **[project page](/projects/academic-hub/marker_conversion/)**. None of this changes what the pipeline converts or how well — it changes how much of a multi-book run can happen without anyone at the keyboard, which is the piece that was missing to run this as a genuinely unattended tool rather than one that just automates the parts between questions.
