---
title: Introducing Academic Hub
summary: "The original August 2026 introduction: connecting scattered course materials, beginning with textbook conversion and plans for sourced answers."
date: 2026-08-18
lastmod: 2026-10-16
authors:
  - me
tags:
  - Academic Hub
  - LLM / RAG
  - Python
image:
  caption: "Illustration: The August 2026 plan had textbook conversion working while search and sourced answers were still planned."
  alt_text: "An August 2026 roadmap shows scattered sources feeding a working textbook converter, followed by search and sourced answers marked as planned."
  focal_point: Center
---

I started Academic Hub to connect the materials I use as a PhD student: textbooks, lecture notes, problem sets, old exams, and research. The goal was more specific than collecting files in one place. I wanted a question in my notes to lead to the relevant textbook explanation, with enough of a source trail to return to the original argument.

<!--more-->

Textbook conversion was the first working part of that plan. A temporary cloud machine could turn dense PDFs into text with mathematical notation and separate figures, then shut down after the batch. The intended next step was a search-and-answer tool that could use those converted passages, rather than ask a model to answer without the course materials.

*Historical note: this introduction describes August 2026. The [current Academic Hub overview](/projects/academic-hub-overview/) explains what was built afterward and where the limits remain.*

At this stage, [Marker PDF Conversion](/projects/academic-hub/marker_conversion/) was running, while [RAG Analysis](/projects/academic-hub/rag_analysis/) was still a design. Its planned role was to find material for direct questions and make that search available to other study tools. Those project links now lead to their current descriptions.

The supporting workspace kept code and bulky source materials separate, so the scripts and this website could be versioned without putting the whole reading collection into their repositories. That organization mattered as a foundation, but it was not yet a complete tutoring system.

The [workspace repository](https://github.com/AaronScherf/ai-sandbox-master) contains the technical structure. This post records the starting point: conversion was useful on its own, and connecting it to searchable explanations was the next piece to build.
