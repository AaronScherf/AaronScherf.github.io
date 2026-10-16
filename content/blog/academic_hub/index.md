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
  caption: "The early Academic Hub plan connects source materials, conversion, and study tools."
---

I started Academic Hub to connect the materials I use as a PhD student: textbooks, lecture notes, problem sets, old exams, and research. The goal was more specific than collecting files in one place. I wanted a question in my notes to lead to the relevant textbook explanation, with enough of a source trail to return to the original argument.

<!--more-->

Textbook conversion was the first working part of that plan. A temporary cloud machine could turn dense PDFs into text with mathematical notation and separate figures, then shut down after the batch. The intended next step was a search-and-answer tool that could use those converted passages, rather than ask a model to answer without the course materials.

[[Insert Image: Create a simple historical project sketch labelled "August 2026". Show scattered textbooks and notes feeding the working textbook converter, then a clearly marked "Planned: search and sourced answers" stage. Use generic documents, three large labels, and no present-day inventory or private materials. Suggested caption: "The first working tool and the study workflow it was meant to support." Suggested alt text: "The August 2026 plan shows textbook conversion working and source-based question answering still planned." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

*Historical note: this introduction describes August 2026. The [current Academic Hub overview](/projects/academic-hub-overview/) explains what was built afterward and where the limits remain.*

At this stage, [Marker PDF Conversion](/projects/academic-hub/marker_conversion/) was running, while [RAG Analysis](/projects/academic-hub/rag_analysis/) was still a design. Its planned role was to find material for direct questions and make that search available to other study tools. Those project links now lead to their current descriptions.

The supporting workspace kept code and bulky source materials separate, so the scripts and this website could be versioned without putting the whole reading collection into their repositories. That organization mattered as a foundation, but it was not yet a complete tutoring system.

The [workspace repository](https://github.com/AaronScherf/ai-sandbox-master) contains the technical structure. This post records the starting point: conversion was useful on its own, and connecting it to searchable explanations was the next piece to build.
