---
title: Study Guide Pipeline
date: 2026-10-11
draft: false
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Source code
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/study_guide
  - type: site
    icon: brands/github
    label: Quiz guide script
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/rag/generate_quiz_guide.py
  - type: site
    icon: brands/github
    label: Quiz guide status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/study_guide/2026-10-05-quiz-study-guide-generation-status.md
  - type: site
    icon: brands/github
    label: Baseline recovery status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-05-wald-guide-recovered-generation-status.md
  - type: site
    icon: brands/github
    label: Comparison run
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-07-study-guide-comparison-status.md
  - type: site
    icon: brands/github
    label: Microeconomics guide status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-09-microecon-hw4-guide-status.md
tags:
  - Python
  - Study Guides
params:
  subproject:
    id: study_guide
    package: agent/study_guide
    code_paths:
      - ai-sandbox/academic-rag-model/agent/study_guide
      - ai-sandbox/academic-rag-model/agent/rag/generate_quiz_guide.py
    readme_path: ai-sandbox/academic-rag-model/agent/study_guide/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/study_guide/2026-10-05-quiz-study-guide-generation-status.md
        role: historical
        lifecycle_ids:
          - study-guide-pipeline
      - path: ai-sandbox/academic-rag-model/docs/status/agent/2026-10-05-wald-guide-recovered-generation-status.md
        role: historical
        lifecycle_ids:
          - study-guide-pipeline
      - path: ai-sandbox/academic-rag-model/docs/status/agent/2026-10-07-study-guide-comparison-status.md
        role: current
        lifecycle_ids:
          - study-guide-pipeline
      - path: ai-sandbox/academic-rag-model/docs/status/agent/2026-10-09-microecon-hw4-guide-status.md
        role: historical
        lifecycle_ids:
          - study-guide-pipeline
    members: []
---

The Study Guide Pipeline turns a course-specific guide specification and indexed notes or textbooks into a cited draft, with optional enhancement and reviewed revision stages.

<!--more-->

A source plan resolves pinned sections and files alongside bounded discovery. Discovered passages wait for review unless an explicit override is used. Drafting records the passages used in the guide's provenance. An optional enhancement pass expands a guide; `revise` proposes targeted edits and produces a review file without changing the guide. `apply-revise` applies accepted edits to a new output and checks that untouched content and citations remain consistent. Cost caps and resumable stage work help control longer runs.

## What the evidence shows

The first comparison tested three draft variants and one enhanced variant on an econometrics guide. The draft-only versions were short and too conceptual for the intended study use; the enhanced version had stronger depth and traceability, but still lacked some exam-oriented structure. The [run report](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-07-study-guide-comparison-status.md) records those judgments and their limited sample. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/study_guide/README.md) notes that a later microeconomics guide also needed an assignment-level coverage and correctness check; a generated guide should be reviewed before relying on it.
