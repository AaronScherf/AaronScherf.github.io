---
title: Study Guide Pipeline
summary: "Build a guide from selected course passages, deepen thin explanations, and review proposed edits before applying them."
date: 2026-10-11
lastmod: 2026-10-16
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

The Study Guide Pipeline builds a guide from selected course materials, then lets me review proposed edits before they change the text. Topics can draw on named textbook sections, particular lecture notes, or newly discovered passages. Keeping that source selection explicit makes it easier to investigate a gap in the finished guide.

<!--more-->

One early run exposed a useful mismatch: a requested textbook section did not cover the statistical test it was supposed to explain. The stronger expanded guide described what that section actually contained and developed the topic from other relevant material. That was more useful than repeating the requested reference as though it were correct.

[[Insert Image: Create a landscape workflow illustration with a clear human review point: "Choose sources" → "Draft guide" → "Review edits" → "Revised guide". At the review stage, show one proposed change accepted and another rejected; retain the original guide beside the revised copy to show that applying decisions creates a new output. Use generic source cards and invented text rather than private notes, actual review decisions, or a fabricated product screenshot. Keep all four stage labels large and make the review point the main visual focus for thumbnail legibility. Suggested caption: "Choose the materials, then decide which revisions to apply." Suggested alt text: "Selected sources become a draft; a person accepts or rejects proposed edits before a revised copy is created." Save the approved image as featured.jpg or featured.png in this page bundle.]]

## From materials to a reviewed guide

I start with a topic list, instructions, and rules for choosing sources. The tool assembles a source plan; newly discovered passages normally wait for review before drafting. The draft records which passages were supplied for each topic, and an optional [enhancement pass](/projects/academic-hub/summary_enhancement/) can develop explanations and worked examples further.

Revision is a separate step. It proposes specific changes for relevance, repetition, correctness, and organization. I can accept or reject them individually. Applying the decisions writes a new guide and checks that untouched passages remain unchanged and that no new page citations have appeared. It also refuses to apply an old review if the guide has changed underneath it.

That approach makes a long guide easier to refine without asking the model to regenerate every section. Spending limits can stop a run between sections or review tasks, and saved revision work can be resumed when its inputs are unchanged.

## What changed in practice

In the first econometrics comparison, three draft-only variants were too short and conceptual for the intended study use. The expanded version supplied deeper derivations and examples, though it still lacked some of the exam-focused structure I wanted. Later topic-based drafts improved the worked problems but also wandered into irrelevant software discussion.

A subsequent review of one draft accepted 27 of 30 proposals. Applying the review made 18 text edits; other accepted items included advisory notes. The run reduced repetition, repaired headings, and added cross-references. An accepted warning can still leave a mathematical issue unresolved when it calls for investigation rather than supplying a correction.

A later microeconomics guide made the remaining gap clear: comparison against the assignment found missing material and errors the revision pass had missed. That check led to hand repairs. The [comparison report](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-07-study-guide-comparison-status.md) and [microeconomics run](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-09-microecon-hw4-guide-status.md) record the observations; the [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/study_guide/README.md) documents the current workflow. A generated guide still needs that final coverage and correctness review before I rely on it.
