---
title: "A Practice Problem Can Have the Right Answer and Still Miss the Point"
summary: "Testing generated exercises revealed two separate questions: does the reasoning hold up, and does it practice the method I asked for?"
date: 2026-09-06
lastmod: 2026-10-19
draft: false
image:
  caption: "Illustration: a useful exercise must practice the intended skill as well as reach a defensible answer."
  alt_text: "An illustrative practice request and draft solution face separate method and reasoning checks; the method is unresolved, while the model's reasoning check still needs human review."
  focal_point: Center
authors:
  - me
tags:
  - Academic Hub
  - Learning Tools
---

One early test of my practice-problem generator produced a flawed proof, then marked its own work valid. Another ignored the requested proof method. For a study tool, both matter: an exercise can reach the expected conclusion without helping me practice what I need to learn.

<!--more-->

The idea behind the [Problem Generation Sub-Agent](/projects/academic-hub/problem_generation/) is appealing. Instead of asking for a generic exercise, it searches my course materials for examples of the topic, style, and difficulty, then drafts a new problem and a worked solution. The [Source Indexer](/projects/academic-hub/source_indexer/) supplies those examples. A second model call checks the result before it reaches me.

That second call was less reassuring than it looked. In the linear algebra trial, the solution treated certain eigenspaces as perpendicular without having the assumptions that would justify it. It also relied on part of the conclusion it was supposed to establish. The checker accepted it anyway. Asking the same small model to read its answer again had not supplied the missing mathematical judgment.

The method problem was easier to isolate. When a request specified a particular kind of proof, the generator kept imitating a different approach in the retrieved examples. Emphasizing the instruction more strongly did not reliably change that behavior. Splitting the verdict into two questions—whether the method matched and whether the mathematics was correct—at least made it possible to reject an answer that passed only one test.

A small comparison then changed the outlook. A cloud-model experiment used the same prompt-building and checking functions on three topics, with three trials each. All nine passed the checks and a hand review found their mathematics sound. The local model had produced no accepted result in two trials of the constrained compactness request. These were different-sized samples on different topic sets, so they are evidence for a useful next experiment, rather than a general model ranking.

Even those nine successes had qualifications. Some proofs used the requested method in a rather superficial way, and two probability problems were almost identical. Correctness, useful practice, and variety remain separate goals. The comparison was also a standalone experiment at this point, not evidence that the cloud route had already been integrated into the tool.

A useful next trial would ask for several different exercises on the same skill, then check both their proofs and whether they demand meaningfully different reasoning. The near-duplicate probability problems show why a string of valid verdicts cannot answer that question.

*Retrospective account prepared October 16, 2026, covering the September 6 milestone. The [status record at that revision](https://github.com/AaronScherf/ai-sandbox-master/blob/5c78c2e3d47939869c2f077e1c479d7500dad832/ai-sandbox/academic-rag-model/docs/2026-09-05-problem-generation-status.md) preserves the trials and their limitations. Project links describe the tools as they have developed since.*
