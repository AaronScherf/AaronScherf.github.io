---
title: "Finding Academic Papers for a Research Library"
summary: "A research tool that finds relevant papers, checks open-access sources, and leaves restricted downloads for the researcher's normal library access."
date: 2026-09-12
authors:
  - me
tags:
  - AI Research Assistant
  - Academic Research
  - Python
image:
  caption: 'Research topics leading to relevant papers and a searchable research library'
  image_suggestion: "Diagram showing a research topic leading to paper metadata, relevance review, open-access sources, and a human handoff for papers that need normal library access."
---

Starting a literature review often means finding candidate papers, deciding which ones matter, and tracking down the full text. I built the [Journal Discovery Pipeline](/projects/ai-research-assistant/journal_discovery/) to help organize those steps and add selected papers to a searchable research library.

<!--more-->

The tool starts with a researcher or a topic, then finds candidate papers through OpenAlex, an academic works catalog. It ranks candidates against a research description on my computer, so I can narrow the list before deciding what to read. It can also suggest newer papers that cite work already in the library; I review those suggestions before anything is added.

For full text, the pipeline checks open-access services and repositories. It can also use an institutionally authorized access route where that is available. If a publisher prevents an automated request, the software stops and leaves the paper for me to open through my usual authenticated browser. It does not try to defeat that restriction. In an early trial, the automatic route obtained 3 of 19 papers; the rest needed a person to retrieve them.

After the papers are available, other parts of the research assistant convert and index them alongside course materials. That makes it possible to search across a focused collection rather than rely on abstracts alone.

This is a way to organize discovery and reading, not a promise that every paper can be fetched automatically. The [project page](/projects/ai-research-assistant/journal_discovery/) explains the sources, access boundaries, tests, and remaining work.
