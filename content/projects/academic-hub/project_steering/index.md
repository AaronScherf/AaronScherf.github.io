---
title: Project Steering
summary: "Turn a long task list into reviewed priorities, while keeping estimates and agent assignments under my control."
date: 2026-10-11
lastmod: 2026-10-16
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

Project Steering helps me choose the next task from a long project list. I review each task's impact, urgency, effort, and dependencies; the tool uses those decisions to produce an explained shortlist. Tasks that still need estimates stay visible in a separate queue.

<!--more-->

Each task keeps its identity when it moves within the list, but suggestions are tied to its wording. If the description changes after an AI agent proposes an estimate or assignment, that proposal becomes stale and needs a fresh review. That keeps an old suggestion from being approved for changed work.

[[Insert Image: Create a landscape illustration showing a long task list becoming a three-item shortlist after owner review. Use three large labels: "Proposed", "Review", "Ready". Show one changed task returning for review and one task waiting for an effort estimate. Use invented task names, without copying the private planning ledger or fabricating a product screenshot. The main idea is that suggestions stay separate from approved priorities. Suggested caption: "A shortlist built from decisions I have reviewed." Suggested alt text: "Task suggestions pass through owner review; changed tasks and missing estimates stay out of the ready shortlist." Save the approved image as featured.jpg or featured.png in this page bundle.]]

The review page also lets me hold a task until a chosen date without changing its priority score. A review of a week-long trial, for example, can remain important while staying out of today's shortlist until the trial finishes. Suggested assignments to coding agents have their own approval step, separate from priority estimates.

Scanning the list makes no AI or network calls and does not edit the source tracker. AI-generated estimates and assignments can be imported for review, but the software never treats them as approved decisions. Choosing or ranking a task does not start its implementation.

An October 10, 2026 scan accounted for 69 active tasks with no unresolved parsing warnings. That establishes coverage of that list, while the quality of the priorities still depends on the estimates and decisions I supply. Many estimates remained unfinished at that checkpoint. Scans currently run on demand; unattended scheduling is still planned. The [status record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-10-project-steering-status.md) and [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/tools/project_steering/README.md) describe the current review rules.
