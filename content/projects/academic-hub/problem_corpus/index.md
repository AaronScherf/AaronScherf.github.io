---
title: Problem Corpus Extraction
date: 2026-09-06
lastmod: 2026-10-16
summary: "Collect scattered exercises while preserving the difference between a question, a student attempt, and a checked answer."
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/problem_corpus
  - type: site
    icon: brands/github
    label: 'Status: Problem Corpus Extraction'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/problem_corpus/2026-09-06-problem-corpus-extraction-status.md
image:
  caption: "Extracted questions retain their source and the status of any accompanying solution."
tags:
  - Python
  - LLM / RAG
params:
  subproject:
    id: problem_corpus
    package: agent/problem_corpus
    code_paths:
      - ai-sandbox/academic-rag-model/agent/problem_corpus
    readme_path: ai-sandbox/academic-rag-model/agent/problem_corpus/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/problem_corpus/2026-09-06-problem-corpus-extraction-status.md
        role: current
        lifecycle_ids:
          - problem-corpus
    members: []
---

A useful practice collection needs more than a list of questions: it needs to say where each question came from and what kind of answer accompanies it. Problem Corpus Extraction gathers exercises from course materials and preserves that distinction. A student's handwritten attempt stays labelled as an attempt.

<!--more-->

That choice came from inspecting the available materials. Some exercises had no answer; others had the student's working beside them, with no basis for calling it an answer key. The stored records therefore mark accompanying text as a student attempt or leave the solution absent. The extractor does not turn an unverified derivation into a verified one.

[[Insert Image: Create a readable question card using an invented elementary exercise. Include large fields "Question", "Source", and "Student attempt—unchecked", with an empty "Answer key" field rather than implying an authoritative solution exists. Show several source documents feeding the collection. Suggested caption: "Keep the question's source and the status of its solution visible." Suggested alt text: "A practice-question card identifies its source and clearly labels accompanying work as an unchecked student attempt." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

A **clearly illustrative card**, rather than an excerpt from private coursework:

> **Question:** Show that the sum of two even integers is even.
>
> **Source:** Example worksheet, Question 2.
>
> **Accompanying work:** Student attempt, not checked.

The tool first detects numbered question boundaries, then asks a model to separate each statement from any accompanying solution and assign a short topic label. It stores the results by course and skips unchanged files on later runs. A failed extraction can be recorded without discarding other successful questions.

A September 2026 math-camp run produced 196 records from eight problem-set files, with no reported extraction failures. Four slide files had no recognized numbered-question boundaries and were skipped. That is evidence of the run's output, not an accuracy audit of all 196 statements or solutions.

The current tool stops at creating the stored collection. Connecting it to [Problem Generation](/projects/academic-hub/problem_generation/) remains separate work; that generator currently retrieves its own examples. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/problem_corpus/README.md) explains the output and provenance rules.
