---
title: Project Steering
date: 2026-10-11
draft: false
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Source code
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/tools/project_steering
  - type: site
    icon: brands/github
    label: Current status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-10-project-steering-status.md
tags:
  - Python
  - Project Planning
params:
  subproject:
    id: project_steering
    package: tools/project_steering
    code_paths:
      - ai-sandbox/academic-rag-model/tools/project_steering
    readme_path: ai-sandbox/academic-rag-model/tools/project_steering/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-10-project-steering-status.md
        role: current
        lifecycle_ids:
          - project-steering
    members: []
---

Project Steering turns the project's to-do tracker into a local, reviewable work view with stable task IDs, owner-controlled priorities, and proposed agent routes.

<!--more-->

An explicit `scan` parses the tracker and writes versioned JSON and Markdown reports without editing the source or calling a model. A local review page lets the owner set impact, urgency, effort, dependencies, status, time gates, and routes. Imported score and route drafts remain suggestions until approved; reviewing a task never starts the work. The system distinguishes a suggested assignment from an owner-approved one, and changed task text invalidates stale proposals.

A live scan on October 10 reported complete coverage of 69 active tasks with no unresolved parser warnings, while local decisions left many tasks needing estimates. Tests cover the implementation and fixtures; those counts do not establish that each priority or route is correct. The [current status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-10-project-steering-status.md) records the queue and remaining owner review. Unattended scheduled scans are a later milestone, not a current feature. See the [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/tools/project_steering/README.md) for commands and decision rules.
