---
title: Making Textbook Conversion Easier to Run in Batches
summary: "Improvements that reduce interruptions during book conversion, catch duplicate material, and recover from some memory failures."
date: 2026-09-22
authors:
  - me
tags:
  - Academic Hub
  - Python
image:
  caption: 'A batch of textbooks moving through conversion with review and recovery steps'
  image_suggestion: "Simple flow showing books checked for duplicates, converted in a batch, and flagged for review or retry when issues occur."
---

Converting a set of textbooks used to require someone nearby to answer repeated prompts and step in when a book exceeded the available machine memory. Recent changes to [Marker PDF Conversion](/projects/academic-hub/marker_conversion/) aim to make batch runs easier to supervise.

<!--more-->

The pipeline can now reuse books that appear to be duplicates and leave uncertain matches for later review. This avoids spending time and computing resources converting the same material again, while keeping a person in the loop when the match is unclear.

It also has a recovery plan for suspected memory failures: retry on the current machine, try a larger one if the failure repeats, and ask for help if that still fails. The failure type is checked before taking those steps, and the recovery state is saved so a restart does not lose track of what has already been tried.

These are implemented safeguards supported by automated tests; they do not mean every large batch has been proven trouble-free in practice. The project page describes the test cases, cost checks, and remaining work under **Testing and Ongoing Development**.
