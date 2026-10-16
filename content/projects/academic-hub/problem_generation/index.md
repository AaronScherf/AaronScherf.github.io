---
title: Problem Generation Sub-Agent
date: 2026-09-06
lastmod: 2026-10-16
summary: "Generate extra course-style practice questions and worked solutions, checking the requested method separately from the answer."
type: academic-hub-project
image:
  caption: "Course examples guide a new problem, followed by separate method and correctness checks."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/problem_gen
  - type: site
    icon: brands/github
    label: 'Status: Problem Generation'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/problem_gen/2026-09-05-problem-generation-status.md
tags:
  - Python
  - LLM / RAG
params:
  subproject:
    id: problem_generation
    package: agent/problem_gen
    code_paths:
      - ai-sandbox/academic-rag-model/agent/problem_gen
    readme_path: ai-sandbox/academic-rag-model/agent/problem_gen/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/problem_gen/2026-09-05-problem-generation-status.md
        role: current
        lifecycle_ids:
          - problem-generation
    members: []
---

Extra practice is most useful when it exercises the method I am trying to learn. Problem Generation uses examples from my course to draft a new question and worked solution, then checks two things separately: whether the solution is mathematically valid and whether it uses the requested technique. A correct proof by a different method may miss the point of the exercise.

<!--more-->

That distinction came from actual trials. A model asked for a proof using explicit error bounds, known as an epsilon-delta argument, kept using a different approach from its retrieved examples. Splitting the review into "requested technique" and "correctness" caught those mismatches, although the local model still failed to produce an accepted answer in two full trials. The check exposed a limitation; it did not make the model capable of solving the task.

[[Insert Image: Show an illustrative practice request becoming a new question and worked solution, followed by two clearly separate review labels: "Requested method?" and "Correct reasoning?" Use a simple sequence-convergence example and identify it as illustrative, not measured output. Include human inspection after the model checks. Suggested caption: "The right answer and the right method are separate checks." Suggested alt text: "A practice problem and solution are reviewed for both the requested technique and mathematical correctness before student inspection." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

An **illustrative request** makes the difference easier to see:

> **Practice question:** Show that the sequence 1/n approaches zero.
>
> **Requested method:** Use the definition of convergence.
>
> **Solution sketch:** For any positive error tolerance ε, choose an integer N greater than 1/ε. Whenever n is larger than N, the distance 1/n from zero is less than ε.

Checking the sketch means inspecting both the inequalities and the use of the definition, rather than accepting a graph or a bare statement of the limit. This is an invented demonstration, not a transcript of a generation trial.

## Course examples guide the draft

The tool retrieves problem-set passages for style and difficulty, plus textbook passages when available. It will not generate without style examples, but can proceed without textbook passages. A weakly related style match can also pull the draft off topic; the closest available example is not necessarily a suitable one.

Generation now defaults to Gemini, with API cost. In the September 6, 2026 comparison, nine trials across three constrained topics passed the model checks and recorded manual review, while the local alternative had struggled with the requested method. That narrow result motivated the default; it does not establish reliable mathematics across a course. Local generation remains optional.

The second check is another model call, so it can repeat the first call's mistakes. Earlier trials accepted flawed reasoning, including a circular argument. Rejected attempts can be revised within a bounded retry loop, but students still need to inspect the result.

The separately extracted [Problem Corpus](/projects/academic-hub/problem_corpus/) is not yet connected to this generation loop. Current examples come through passage retrieval. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/problem_gen/README.md) documents that distinction and the generation options.
