---
title: Guided Solutions
summary: "Keeping my own reasoning, AI-written derivations, and proofs developed through tutoring together with clear authorship."
date: 2026-10-11
lastmod: 2026-10-16
draft: false
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Workflow and run audit
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/problem_sets/2026-10-06-guided-solutions-proof-pipeline-status.md
tags:
  - Study Guides
  - Learning Tools
image:
  caption: "Illustration: three contributions to a solution, with their authorship kept visible."
  alt_text: "A problem-set question with separate spaces for student reasoning, an AI derivation, and a proof developed through tutoring."
  focal_point: Center
params:
  subproject:
    id: guided_solutions
    package: agent/problem_sets (operational workflow)
    code_paths: []
    readme_path: null
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/problem_sets/2026-10-06-guided-solutions-proof-pipeline-status.md
        role: current
        lifecycle_ids:
          - guided-solutions
    members: []
---

Guided Solutions brings three contributions to a problem set together: an AI-written derivation, space for my own intuition, and a proof developed through tutoring. Each has its own labelled block, so I can compare approaches and see whose reasoning I am reading.

<!--more-->

The separation matters when the routes differ. In the recorded microeconomics run, the agent supplied detailed reference proofs; later tutoring on two questions produced more compact proofs following the student's approach. Both were kept, with room for the student's interpretation alongside them.

An **illustrative layout**, rather than an excerpt from the private coursework, looks like this:

> **My reasoning:** I think adding another option changes the chance of choosing the default, but I need to identify why.
>
> **Agent derivation:** Work through the choice probabilities under the question's stated rule, showing the intermediate steps.
>
> **After tutoring:** Record the proof developed during the discussion and compare its key step with the reference derivation.

To prepare a document, I use the assignment and a question-by-question hints sheet to organize the work. The [transcription tools](/projects/academic-hub/notes_transcription/) make lecture notes available to the [Source Indexer](/projects/academic-hub/source_indexer/), which finds the course's definitions and notation alongside textbook passages. The agent is instructed to show its algebra and assumptions, while leaving the student's writing intact. A later audit checks the document's structure and mathematical work.

This is a procedure I direct using the existing conversion, search, and tutoring tools. The [run audit and workflow](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/problem_sets/2026-10-06-guided-solutions-proof-pipeline-status.md) records one completed problem-set run and its tutoring follow-up. It provides a playbook for another assignment; each new solution still needs review. The course documents remain private, and the workflow has no dedicated automated test suite.
