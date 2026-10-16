---
title: Tutor Diagnosis & Hint Generator
date: 2026-09-28
lastmod: 2026-10-16
summary: "Get a hint, examine an attempt on separate reasoning criteria, and compare another solution without treating it as a final verdict."
type: academic-hub-project
image:
  caption: "Hints, feedback, and a separate solution help review a student attempt."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/rag
  - type: site
    icon: brands/github
    label: Source code
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/rag/tutor_diagnosis.py
  - type: site
    icon: brands/github
    label: 'Status: Tutor Diagnosis'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-09-27-tutor-diagnosis-status.md
tags:
  - Python
  - LLM / RAG
  - EdTech
params:
  subproject:
    id: tutor_diagnosis
    package: agent/rag (tutor diagnosis)
    code_paths:
      - ai-sandbox/academic-rag-model/agent/rag/tutor_diagnosis.py
    readme_path: ai-sandbox/academic-rag-model/agent/rag/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-09-27-tutor-diagnosis-status.md
        role: current
        lifecycle_ids:
          - tutor-diagnosis
    members: []
---

A correct conclusion can hide a gap in the argument, while an otherwise sound attempt may use a method the course has not introduced. Tutor Diagnosis examines those differences separately: whether the result is right, whether the steps are justified, and whether the explanation fits the course's definitions and methods. Its scores are model feedback for review, not instructor grades.

<!--more-->

The tool can also give a hint before I have a full attempt. It searches course material for a useful direction and aims to leave the final derivation to me. When the available passages do not cover the topic, it labels a general hint instead of attaching an unsupported course reference.

[[Insert Image: Create an illustrative attempt → hint → revised attempt sequence using a simple invented mathematical claim. Beside the revision show three large review labels: "Result", "Reasoning", and "Course fit". Keep the hint distinct from a complete solution and label the scores as feedback rather than grades. Use no private assignment or fabricated application screenshot. Suggested caption: "Review the argument, not just its final answer." Suggested alt text: "A student revises an attempt after a hint, then reviews separate feedback on the result, reasoning, and fit with the course." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

An **illustrative learning loop**, not a transcript or a new test result:

> **Claim:** Every even integer is divisible by four.
>
> **Attempt:** It works for 4 and 8, so it must hold for all even integers.
>
> **Hint:** What would you need to check beyond those two examples?
>
> **Revision:** Two is even but not divisible by four. One counterexample disproves the claim.

The point is to identify the reasoning gap: examples that support a claim do not establish that it holds in every case. For course problems, the tool compares an attempt with a reference answer and retrieved passages, then names the most important gap to revisit.

## A fresh solution for comparison

A separate solver receives the question without the tutor's earlier answer or the source passages used to write it. In a recorded econometrics trial, this second solution identified an intercept condition the first answer had omitted. The user still compares both arguments; agreement or disagreement is not automatically resolved into a verdict.

Other recorded checks included identifying an intentionally flawed regression argument and producing a hint on a microeconomics problem without a final derivation. Those are limited examples of the workflow, not evidence that feedback will be accurate on every assignment.

Course-scoped logs preserve attempts, hints, feedback, and solution comparisons for later summaries. The [status record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-09-27-tutor-diagnosis-status.md) describes the trials. This is a set of tools within [RAG Analysis](/projects/academic-hub/rag_analysis/); the separate [Socratic Tutor](/projects/academic-hub/socratic_tutor/) tracks an interactive session and applies different conversation rules.
