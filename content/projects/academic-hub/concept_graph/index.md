---
title: Concept Graph
summary: "Explore how course ideas connect, including the conditions a theorem needs and the source passages behind each proposed connection."
date: 2026-10-11
lastmod: 2026-10-16
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

Concept Graph maps the ideas in a course and the conditions that connect them. An arrow can say that one idea implies another, but it also records the assumption needed to make that claim. Selecting it gives me a sentence to examine and references to the course material behind it.

<!--more-->

For example, the package's sample graph connects a **partial order** to a **total order** when every pair can be compared. A partial order can leave two items unranked relative to one another; adding that comparison requirement produces a total order. The condition on the arrow explains what changed, rather than leaving me to infer it from two nearby boxes.

[[Insert Image: Create a focused landscape diagram based on the sample-graph example above, rather than a screenshot of the entire crowded graph. Show "Partial order" leading to "Total order" only when "Every pair can be compared"; place that condition directly on the connection. Include a small source-reference symbol and a visible "Proposed" label to communicate that connections have supporting material and still need review. Present it as an explanatory illustration, not a verified claim or an exact reproduction of the live interface. Use large labels, high contrast, and ample space so the condition remains readable on a phone and the two concepts remain recognizable in a thumbnail. Suggested caption: "The condition on a connection explains what is needed to reach the next idea." Suggested alt text: "A proposed connection from partial order to total order, conditional on every pair being comparable, with a source-reference symbol." Save the approved image as featured.jpg or featured.png in this page bundle.]]

The first full graph covers the first half of a graduate microeconomic theory sequence: [open the live graph](https://aaronscherf.github.io/microecon-concept-graph/). As of October 15, 2026, it contains 104 concepts and 159 connections across eight course sections. Those counts describe the draft's scale; the explanations and connections still need review.

## Following an idea

Each box represents an idea, such as a definition, theorem, or example. Selecting it opens an explanation, its mathematical statement, and its connections written out in words. Course-section filters and several layouts help narrow a crowded graph to the part I want to study.

That makes the graph useful for tracing a result back through the assumptions and definitions it depends on. Section summaries offer another way in, though those summaries are AI drafts and some wording is looser than the underlying theory.

## Building and reviewing the connections

An AI agent drafts explanations and connections from task cards containing passages retrieved from lecture notes, slides, assignments, and textbooks. Code then checks the submitted structure: references must come from the supplied passages, required conditions must be present, and circular definition chains are rejected. Those checks catch structural problems; a cited passage can still be misinterpreted.

The drafts remain marked as proposed until a person accepts or edits them. Reviewers can comment, reject a connection, or suggest a missing idea through the page. Suggestions from several reviewers are combined before the maintainer handles them. Submission through GitHub has not yet been tested from start to finish.

## Evidence and limits

The October 15 status records 331 Python tests, 45 viewer tests, browser checks, and a graph built from actual course materials. These establish different things: the tests exercise the software, while the graph shows what the drafting process produced. Neither establishes a learning benefit.

The same model drafts and critiques the connections, so its review may be lenient. Human review or a second model is still needed to assess the content. The [current status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-15-concept-graph-status.md) records the open issues; the [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/concept_graph/README.md) explains how the graph is built and reviewed.
