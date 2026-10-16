---
title: "Finding Academic Papers for a Research Library"
summary: "How I find candidate papers, narrow them to a research question, and keep track of the full text I still need to obtain."
date: 2026-09-12
lastmod: 2026-10-15
authors:
  - me
tags:
  - AI Research Assistant
  - Academic Research
  - Python
image:
  caption: 'Research topics leading to relevant papers and a searchable research library'
---

Starting a literature review often means finding candidate papers, deciding which ones matter, and tracking down the full text. I built the [Journal Discovery Pipeline](/projects/ai-research-assistant/journal_discovery/) to help organize those steps and add selected papers to a searchable research library.

<!--more-->

The tool starts with a researcher or a topic, then finds candidate papers through OpenAlex, a catalog of academic publications. It compares them with a description of what I'm looking for, so I can narrow the list before deciding what to read. That comparison runs on my computer. It can also suggest newer papers that cite work already in the library; I review those suggestions before anything is downloaded.

For full text, the tool checks services that provide freely available copies of papers. It can also try my university's library access where that is available. If a publisher blocks the automated request, the paper goes on a list for me to open through my usual library login. In an early trial, the automatic route obtained 3 of 19 papers; the rest needed a person to retrieve them.

After the papers are available, separate conversion and search tools add their text to the research library. I can then search the papers alongside course materials, with access to more than their abstracts.

*Update, October 15, 2026:* A later trial searched for papers about disaster resilience, response, and recovery. Fifteen candidates passed the relevance filter, and a review found all fifteen on topic. Seven downloaded automatically; the other eight were left for manual access. That is a useful distinction in practice: finding a relevant paper and obtaining its full text are separate steps.

The [project page](/projects/ai-research-assistant/journal_discovery/) describes the search sources, results, and remaining work.
