---
title: Making Textbook Conversion Easier to Run in Batches
summary: "Reusing a textbook across courses and recovering from memory failures make conversion batches easier to supervise."
date: 2026-09-22
lastmod: 2026-10-15
authors:
  - me
tags:
  - Academic Hub
  - Python
image:
  caption: 'A batch of textbooks moving through conversion with review and recovery steps'
  alt_text: 'Illustrated flowchart of duplicate detection, textbook conversion scheduling, and responses to out-of-memory failures.'
---

Converting a set of textbooks used to require someone nearby to answer repeated prompts and step in when a book exceeded the available machine memory. Recent changes to [Marker PDF Conversion](/projects/academic-hub/marker_conversion/) aim to make batch runs easier to supervise.

<!--more-->

The same textbook PDF might appear in the reading folders for two courses. If it has already been converted for one, the tool can reuse that output for the other. A fingerprint of the file's contents recognizes an exact duplicate even if someone has renamed it.

Very close title-and-author matches can also be reused and logged for later confirmation; less certain matches need a decision first. This policy reflects a cost tradeoff: mistaken reuse can be reversed, while rented GPU time spent converting a duplicate is already gone. Review remains important, but every likely duplicate need not interrupt the batch.

The recovery procedure first checks whether a failed conversion ran out of memory. If that is the cause, the next steps are to reset and retry on the current machine, then try a larger one if the failure repeats. If that also fails, it calls for help. The run record preserves what has already been tried.

The person or coding agent running the conversion follows that procedure. Automated tests cover the supporting code, while reliability across large batches still needs observation. The [project page](/projects/academic-hub/marker_conversion/) describes what has been tested, the cost checks, and the remaining work.
