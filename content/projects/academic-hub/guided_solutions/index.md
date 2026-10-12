---
title: Guided Solutions
date: 2026-10-11
draft: true
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Workflow and run audit
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/problem_sets/2026-10-06-guided-solutions-proof-pipeline-status.md
tags:
  - Study Guides
  - Learning Tools
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

Guided Solutions is a human-directed workflow for turning a problem set, course sources, and tutoring work into a structured solutions document. It is an operational procedure, not a standalone executable package.

<!--more-->

The documented run used transcribed lecture material and the retrieval index to support formal, source-grounded proofs. Separate blocks distinguish agent-written derivations, the student's own intuition, and later tutor-session solutions. A hints document supplies a question-by-question structure, and a quality audit checks the resulting work. Keeping these roles explicit makes the document useful for comparison and later review without presenting agent output as the learner's work.

The [run audit and workflow](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/problem_sets/2026-10-06-guided-solutions-proof-pipeline-status.md) describes a completed microeconomics problem-set run and a subsequent tutoring integration. It is evidence for that run and a replicable playbook, not evidence that a general automated solutions pipeline or dedicated test suite has shipped. The underlying course documents stay in the private notes vault.
