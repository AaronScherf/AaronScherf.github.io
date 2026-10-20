---
title: "Finding Academic Papers for a Research Library"
summary: "Comparing abstracts with a research question and following citation trails to build a focused paper library."
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
  alt_text: 'Flowchart follows research topics through paper discovery, local relevance scoring, full-text retrieval, and manual follow-up for inaccessible papers.'
---

Starting a literature review often means finding candidate papers, deciding which ones matter, and tracking down the full text. I built the [Journal Discovery Pipeline](/projects/ai-research-assistant/journal_discovery/) to help organize those steps and add selected papers to a searchable research library.

<!--more-->

The tool starts with a researcher or a topic, then finds candidate papers through OpenAlex, a catalog of academic publications. A model on my computer turns my research description and candidate abstracts into text embeddings: numerical representations used to compare meaning. Comparing those representations gives each candidate a relevance score before any download begins. This scoring stage makes no paid AI calls.

The library can also become a starting point for discovery. The tool follows citations forward to find newer papers that cite work I've already collected, scores those candidates, and proposes a reading list. I review that list before anything is downloaded.

For full text, the tool tries several services for freely available copies in turn, so one service missing a paper does not end the search. It can also try my university's library access where that is available. If those routes fail, the paper goes on a list for me to open through my usual library login. In an early trial, the automatic route obtained 3 of 19 papers; the rest needed a person to retrieve them.

After the papers are available, separate conversion and search tools add their text to the research library. I can then search the papers alongside course materials, with access to more than their abstracts.

*Update, October 15, 2026:* A later trial searched for papers about disaster resilience, response, and recovery. Fifteen candidates passed the relevance filter, and a review found all fifteen on topic. Seven downloaded automatically; the other eight were left for manual access. That is a useful distinction in practice: finding a relevant paper and obtaining its full text are separate steps.

The [project page](/projects/ai-research-assistant/journal_discovery/) describes the search sources, results, and remaining work.
