---
title: Socratic Tutor
date: 2026-10-11
draft: true
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Source code
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/tutor
  - type: site
    icon: brands/github
    label: Status and live-run findings
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/tutor/2026-10-08-socratic-tutor-status.md
tags:
  - Python
  - Learning Tools
params:
  subproject:
    id: socratic_tutor
    package: agent/tutor
    code_paths:
      - ai-sandbox/academic-rag-model/agent/tutor
    readme_path: ai-sandbox/academic-rag-model/agent/tutor/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/tutor/2026-10-08-socratic-tutor-status.md
        role: current
        lifecycle_ids:
          - socratic-tutor
          - socratic-tutor-v1-1
    members: []
---

The Socratic Tutor is a local session gate for AI-assisted office hours. It tracks what a learner has established, checks the agent's next reply against tutoring rules, and records the session and learner profile.

<!--more-->

The agent conducts the conversation, while the Python CLI maintains an append-only event log and a state machine. Preparation produces a reviewed problem packet with claims, a glossary, rubric, and sealed solution steps. During a session, `turn` records the learner's message and returns a brief; `say` checks a draft response before it is sent. The solution steps are released for a quoted step check only when verification is available. Pause, skip, defer, revisit, and audit commands cover interrupted and incomplete work.

## What the evidence shows

Automated tests cover the session rules and CLI. Two live sessions on one problem set exercised the skip, defer, pause, and definition-relay paths. They also exposed a teaching limitation: strict claim checking kept the tutor from explaining material the learner had not yet established, making it better at assessment than instruction in those runs. Some claim recognizers fired on unrelated phrases, and ratings could credit weak evidence. A more permissive teaching mode and wider live validation are still design questions, not shipped outcomes.

The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/tutor/README.md) describes the commands and known limits; the status record above details the live observations.
