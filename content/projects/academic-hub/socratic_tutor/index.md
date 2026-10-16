---
title: Socratic Tutor
summary: "Track the reasoning a student has established and check the tutor's next reply against it—with a clear limit when new material needs explaining."
date: 2026-10-11
lastmod: 2026-10-16
draft: false
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Source code
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/tutor
  - type: site
    icon: brands/github
    label: Status and live-run findings
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/tutor/2026-10-08-socratic-tutor-status.md
tags:
  - Python
  - Learning Tools
params:
  subproject:
    id: socratic_tutor
    package: agent/tutor
    code_paths:
      - ai-sandbox/academic-rag-model/agent/tutor
    readme_path: ai-sandbox/academic-rag-model/agent/tutor/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/tutor/2026-10-08-socratic-tutor-status.md
        role: current
        lifecycle_ids:
          - socratic-tutor
          - socratic-tutor-v1-1
    members: []
---

The Socratic Tutor gives an AI study conversation a record of which steps the student has established. Before the tutor sends a reply, a local program checks it against that record and rules intended to hold back unreached solution steps. The conversation can then be reviewed against what the student actually said.

<!--more-->

That restraint also exposed the central difficulty. In two recorded sessions on one microeconomics problem set, the tutor followed several session rules but struggled to teach unfamiliar material: an explanation could itself reveal a step the student had not reached. The system was better at assessing existing understanding than helping a learner build it.

[[Insert Image: Create a landscape illustration of a tutoring turn with three large elements: "Student's reasoning", "Reply check", and "Tutor's next question". Show a small record of established steps feeding the check, with one unreached solution step held back. Include a modest label "Current limit: explaining new material" so the picture does not imply that the teaching limitation is solved. Use invented generic notes and no private coursework or fabricated chat screenshot. Suggested caption: "Check the next reply against what the student has established." Suggested alt text: "A student's reasoning updates a record of established steps, which is used to check the tutor's next question before sending it." Save the approved image as featured.jpg or featured.png in this page bundle.]]

An **illustrative version of that failure pattern** is:

> **Student:** I don't understand why this condition matters.
>
> **Tutor:** Which part of the condition could you use?

Another question preserves the student's chance to solve the problem, but it may provide little help with the missing concept. A more permissive teaching mode is still a design direction, not an observed solution to this problem.

## What the program keeps track of

An AI agent conducts the dialogue; the Python program maintains the session record and checks proposed replies locally, without asking another model to judge every turn. Preparation defines the problem's key claims, reference steps, glossary, and review criteria. During the conversation, word-pattern checks look for evidence that the student has established a claim or encountered a known pitfall.

When enough progress has been recorded, the reference steps are released for a comparison using quotations from the student's messages. Pausing saves the transcript, summary, and learner record. Skip and defer rules allow incomplete parts to be parked, though the live runs found that returning to a parked question was too rigid.

The checks have limits: unfamiliar wording can be missed, unrelated phrases can trigger a match, and an agent can credit weak evidence. They provide an inspectable record rather than a guarantee against revealing an answer or misjudging understanding. Automated tests exercise the session rules; the [live-run findings](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/tutor/2026-10-08-socratic-tutor-status.md) explain what happened in the two sessions. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/tutor/README.md) documents the current workflow.

For a hint or feedback on a single attempt, [Tutor Diagnosis](/projects/academic-hub/tutor_diagnosis/) offers those tools within RAG Analysis. [Guided Solutions](/projects/academic-hub/guided_solutions/) describes a document workflow for keeping my reasoning and later tutoring work beside an agent's reference derivation. Those are useful alternatives when I need a specific study task rather than a tracked conversation.
