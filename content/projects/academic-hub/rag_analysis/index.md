---
title: RAG Analysis
date: 2026-08-30
lastmod: 2026-10-16
summary: "Answer questions from course passages and keep references that help inspect the explanation and its sources."
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/rag
  - type: site
    icon: brands/github
    label: 'Status: Rag Agent'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-08-30-rag-agent-status.md
  - type: site
    icon: brands/github
    label: 'Status: Question Resolver'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-10-03-question-resolver-status.md
tags:
  - Python
  - LLM / RAG
image:
  caption: "A question leads to relevant passages, an explanation, and references to inspect."
params:
  subproject:
    id: rag
    package: agent/rag
    code_paths:
      - ai-sandbox/academic-rag-model/agent/rag
    readme_path: ai-sandbox/academic-rag-model/agent/rag/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-08-30-rag-agent-status.md
        role: current
        lifecycle_ids:
          - rag-agent
      - path: ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-10-03-question-resolver-status.md
        role: current
        lifecycle_ids:
          - question-resolver
    members: []
---

RAG Analysis answers a question using passages found in my textbooks and course notes, with references back to the material it used. That lets me inspect an explanation and continue reading at its source. The reference is a starting point for checking the answer, not a guarantee that the model interpreted it correctly.

<!--more-->

One useful choice is limiting how many passages a single file can contribute. Otherwise, a relevant textbook can fill the available space and crowd out lecture notes or another author's explanation. Follow-up questions are also rewritten using the recent conversation, so "explain that differently" becomes a specific question the search tools can use.

[[Insert Image: Show a question connected to two source passages and a short answer with a readable section/page reference. Use invented text and clearly label it illustrative; do not fabricate a screenshot or imply the reference proves the answer. Make the two-source comparison and the route back to a source page visible at thumbnail size. Suggested caption: "Keep an explanation connected to the passages used to write it." Suggested alt text: "Two source passages support an illustrative answer with a section and page reference that can be checked." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

A **clearly illustrative example**, rather than a quotation from a recorded answer:

> **Question:** What does the spectral theorem help explain about a real symmetric matrix?
>
> **Answer sketch:** It gives perpendicular directions along which the transformation acts by scaling, making its action easier to describe.
>
> **Reference format:** Section 7.4, pages 264–266.

The name RAG means **retrieval-augmented generation**: find relevant passages first, then supply them to the model writing the answer. This project reuses the [Source Indexer](/projects/academic-hub/source_indexer/) for that search. An August 2026 trial answered a spectral-theorem question using two source files; a follow-up exchange also exercised the conversation-based search step. Those were specific trials, not a broad evaluation of answer accuracy.

## What is remembered

The running chat retains its conversation, but restarting the process does not restore the full dialogue. With a course selected, the tool can save answer, hint, draft-feedback, and verification events. Recent recorded learning gaps can inform later answers, and those events can be summarized into a study note. A requested report can also save an answer and its references. These records survive separately from the live chat history.

A companion resolver answers question markers in handwritten notes. Its recorded seven-question run included four source-grounded answers and three marked as ungrounded. General answers remain leads to check, and retrieving a handful of passages is too narrow to establish comprehensive coverage of a week's study.

The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/rag/README.md) describes the current interfaces. [Tutor Diagnosis](/projects/academic-hub/tutor_diagnosis/) adds feedback on an attempt; the separate [Socratic Tutor](/projects/academic-hub/socratic_tutor/) manages an ongoing tutoring session.
