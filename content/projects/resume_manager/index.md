---
title: Resume Manager
date: 2026-09-09
lastmod: 2026-10-16
summary: "Tailor a resume from a maintained record of experience, preserving fixed details and saving checks alongside each application."
image:
  caption: "Illustration: Change the emphasis while keeping the record of experience fixed."
  alt_text: "A structured master resume supplies fixed facts while a job description guides bullet wording; the resulting draft includes review checks."
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/resume_manager
  - type: site
    icon: brands/github
    label: 'Status: Resume Manager'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/resume_manager/2026-09-09-resume-manager-status.md
  - type: site
    icon: brands/github
    label: 'Status: Resume Manager Tailoring Guidance'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/resume_manager/2026-09-28-resume-manager-tailoring-guidance-status.md
tags:
  - Python
  - LLM / RAG
params:
  subproject:
    id: resume_manager
    package: resume_manager
    code_paths:
      - ai-sandbox/academic-rag-model/resume_manager
    readme_path: ai-sandbox/academic-rag-model/resume_manager/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/resume_manager/2026-09-09-resume-manager-status.md
        role: current
        lifecycle_ids:
          - resume-manager
      - path: ai-sandbox/academic-rag-model/docs/status/resume_manager/2026-09-28-resume-manager-tailoring-guidance-status.md
        role: current
        lifecycle_ids:
          - resume-tailoring
    members: []
---

A useful tailored resume changes the emphasis without changing the experience. Resume Manager keeps a master record of my roles, projects, and accomplishments, then uses a job description to select relevant experience and rewrite its bullets. Employer names, dates, and locations are copied by code from the master; the model supplies bullet wording rather than rebuilding the whole document.

<!--more-->

The most effective change was removing AI from the first step. My source resume already had recognizable sections, but model-based extraction misplaced fields and omitted information. A conventional parser that reads those sections reduced the recorded bootstrap time from over 90 minutes to about 1.5 seconds on my resume. Language generation remains useful for tailoring; it was unnecessary for reading a layout the code could recognize directly.

## What tailoring can change

An **illustrative example for a hypothetical applicant** applying to a monitoring role:

> **Master:** Prepared monthly monitoring reports in Excel covering 12 projects.
>
> **Tailored for a role emphasizing Excel:** Prepared Excel monitoring reports for 12 projects each month.

The revised bullet puts Excel first while keeping the frequency, activity, and project count fixed. It adds no claim of managing those projects or improving their results. That is the kind of distinction I still review in the actual output; fixed dates alone cannot protect every factual implication of a rewritten sentence.

The ordinary workflow uses a saved job description and a local model. Optional questions let me explain priorities before tailoring, and the application folder keeps that guidance alongside the job description, draft, PDF, and validation report. A separate route can interpret a rough opportunity description and request a cloud-based relevance brainstorm. That route may send resume material to Gemini; the saved-description route does not require it.

## Check what survived the rewrite

Checks flag possible invented or dropped numbers, repeated openings, similar bullets, and some unsupported responsibility wording. Explicitly supplied facts can include required phrases or acceptable alternatives, making omissions easier to spot. These are advisory checks, not a full understanding of whether the resume is faithful.

The September 2026 application trials showed why that matters: a rewrite dropped a financial figure, and another output omitted qualitative guidance despite a clean numeric report. Newer checks cover more of those cases, but word matching and similarity tests can still miss changes in meaning.

Page fitting ranks candidate experience and measures rendered drafts against a target length, so content selection responds to the available space. I still inspect the final PDF for readable layout and omissions. The master remains maintained by hand, and tailoring never submits an application. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/resume_manager/README.md) explains the current entry points and review outputs.
