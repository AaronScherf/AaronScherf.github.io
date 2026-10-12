---
title: Concept Graph
date: 2026-10-11
draft: true
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Source code
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/concept_graph
  - type: site
    icon: brands/github
    label: Core status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-09-concept-graph-core-status.md
  - type: site
    icon: brands/github
    label: Drafting and seed-run status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-10-concept-graph-pipeline-status.md
tags:
  - Python
  - Learning Tools
params:
  subproject:
    id: concept_graph
    package: agent/concept_graph
    code_paths:
      - ai-sandbox/academic-rag-model/agent/concept_graph
    readme_path: ai-sandbox/academic-rag-model/agent/concept_graph/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-09-concept-graph-core-status.md
        role: current
        lifecycle_ids:
          - concept-graph-core
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-10-concept-graph-pipeline-status.md
        role: current
        lifecycle_ids:
          - concept-graph-pipeline
    members: []
---

Concept Graph is a course study aid that shows concepts and their typed, conditional relationships in a single browsable HTML page.

<!--more-->

The Python package validates graph data, builds the viewer, and supports human review of proposed nodes and edges. Drafting stages can seed an outline, fill explanations, link concepts, and critique proposed links using corpus evidence. Their outputs remain proposed until a person reviews them; only human acceptance or editing marks an item verified. The graph data and built page live in a separate graph repository, while private task cards with source passages stay outside it.

The core and drafting stages have fixture-based tests. A real microeconomics seed run reached 59 nodes in eight sections after three passes, with all configured required concepts present and no validation errors. The [pipeline status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-10-concept-graph-pipeline-status.md) also records missing topics and placement concerns for human review. That seed run does not establish live-corpus quality for fill, link, or critic. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/concept_graph/README.md) describes the data model and review commands.
