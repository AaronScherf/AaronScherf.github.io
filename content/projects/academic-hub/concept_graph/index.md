---
title: Concept Graph
date: 2026-10-11
draft: false
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Source code
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/concept_graph
  - type: site
    icon: brands/github
    label: Current status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-15-concept-graph-status.md
  - type: site
    icon: brands/github
    label: Core status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-09-concept-graph-core-status.md
  - type: site
    icon: brands/github
    label: Drafting and seed-run status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-10-concept-graph-pipeline-status.md
  - type: site
    icon: brands/github
    label: Reviewer proposals status (historical)
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-14-concept-graph-proposals-status.md
  - type: site
    icon: globe
    label: Live concept graph
    url: https://aaronscherf.github.io/microecon-concept-graph/
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
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-14-concept-graph-proposals-status.md
        role: historical
        lifecycle_ids:
          - concept-graph-proposals
          - concept-graph-viewer
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-15-concept-graph-status.md
        role: current
        lifecycle_ids:
          - concept-graph-proposals
          - concept-graph-viewer
    members: []
---

Concept Graph is a course study aid that shows concepts and their typed, conditional relationships in a single browsable HTML page. The first graph covers the first half of a graduate microeconomic theory sequence: [open the live graph](https://aaronscherf.github.io/microecon-concept-graph/).

<!--more-->

## What it is

Each box is a concept (a definition, axiom, theorem or standard example), coloured by course section; each arrow is a typed claim such as "is a", "defined on", "implies" or "yields", with its condition and its citations. Selecting a concept shows its explanation, its formal statement and every connection written out as a sentence. The graph currently holds 104 concepts and 159 linked claims in eight course sections, from order theory and preferences through revealed preference, stochastic choice, consumer demand, duality, producer theory and choice under risk.

## How it is built

The Python package validates graph data, builds the page, and runs a drafting pipeline in stages: seed an outline, fill explanations, link concepts, critique the links, and summarise each section. Each stage writes task cards that carry the evidence passages (retrieved from the course notes, slides, homework, earlier years' material and textbooks); an agent fills the cards; and code checks every result before it is applied: citations must come from the offered passages, prose must be in the agent's own words, and cycles in definitional chains are rejected. Drafting runs on a subscription agent rather than a metered API, with Claude coordinating and reviewing.

Everything the pipeline writes stays proposed until a person reviews it. The page lets a reviewer accept, reject, edit or comment, and propose a missing concept or connection with a few dropdowns; proposals from several reviewers are merged and de-duplicated before a maintainer sees them.

## The page

- Section buttons filter the graph, select their concepts and show an agent-drafted summary of the section.
- Concepts can be multi-selected (Ctrl or Shift-click, a box, a whole section), moved together, and turned into proposed connections.
- The concept list collapses by section; layouts can be switched between a spread-out view, section rows, section clusters and a course timeline.

## Evidence and limits

The core and drafting stages have fixture-based tests (331 Python and 45 viewer tests), and the page behaviour is checked in a headless browser. The graph is a real run over the course corpus, and every claim cites the passages it was drafted from. Limits worth knowing: the critic stage uses the same model that drafted the claims, so its verdicts are probably lenient and a sample should be reviewed by a person or another model; the section summaries are agent-drafted and not yet reviewed; and the reviewer submission path through GitHub has not been exercised end to end. The [current status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-15-concept-graph-status.md) records the open items, and the [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/concept_graph/README.md) describes the data model and review commands.
