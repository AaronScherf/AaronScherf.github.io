---
title: Visualization Sub-Agent
date: 2026-09-03
lastmod: 2026-10-16
summary: "Add an interactive mathematical plot to a sourced explanation, using a prepared template or generated chart code."
type: academic-hub-project
image:
  caption: "An interactive plot accompanies an explanation and its source references."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/viz
  - type: site
    icon: brands/github
    label: 'Status: Visualization Agent'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/viz/2026-09-02-visualization-agent-status.md
tags:
  - Python
  - LLM / RAG
params:
  subproject:
    id: visualization
    package: agent/viz
    code_paths:
      - ai-sandbox/academic-rag-model/agent/viz
    readme_path: ai-sandbox/academic-rag-model/agent/viz/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/viz/2026-09-02-visualization-agent-status.md
        role: current
        lifecycle_ids:
          - visualization
          - viz-example-store
          - viz-ollama-retry
    members: []
---

A formula for gradient descent describes repeated steps toward a minimum. A picture can show what those steps do: the prepared example in this tool traces a path across the contours of a bowl-shaped surface toward its center. I can zoom in and inspect the points alongside the written explanation, rather than infer the whole path from the update rule.

<!--more-->

The important distinction is how that picture is made. A small library covers familiar concepts with prepared Plotly charts, which run without a chart-generation model call. For other topics, the tool asks a model to write chart code using the question and retrieved course passages. That opens up more concepts, but introduces another judgment: a script can run successfully while illustrating the wrong idea.

[[Insert Image: Capture the existing gradient-descent template using standard plotting tools, showing its actual contour surface and descent path. Pair a close readable crop with the formula f(x, y) = x² + 2y² and a short explanation of the path toward the origin. Do not invent a step-size slider or use generated artwork to stand in for a mathematical plot. Suggested caption: "Inspect the steps as they approach the minimum." Suggested alt text: "A gradient-descent path curves across the contours of a bowl-shaped function toward its minimum at the origin." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

## A plot beside the answer

Visualization is optional within [RAG Analysis](/projects/academic-hub/rag_analysis/). A report can combine the question, answer, source references, and interactive chart in one HTML file. If chart generation fails, the text report can still be produced. A recorded September 6, 2026 trial combined a [generated practice problem](/projects/academic-hub/problem_generation/), its solution, and an embedded interactive plot in the same report.

Generated charts currently use Gemini by default, with API cost. Local Ollama generation is an explicit alternative, but it timed out or produced broken scripts in the recorded comparison. Gemini succeeded twice on the same request. Two successes are useful evidence for that change of default, not a broad chart-accuracy evaluation.

## Running code is one check

The tool executes generated code with a time limit, a separate working directory, and an environment that excludes inherited API secrets. Execution errors can be returned to the model for a bounded retry. These measures limit particular failure modes; the process is not a comprehensive security sandbox.

Past scripts that ran successfully can be offered as examples to later generation. They stay separate from the prepared templates because successful execution alone does not make an example mathematically correct. Whether that small example store improves results over sustained use remains unmeasured.

Template matching also needs care: "convergence in probability" should not receive a generic series-convergence plot just because both contain the same word. Inspecting what the chart represents remains part of using it. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/viz/README.md) explains templates, generation, and the execution limits.
