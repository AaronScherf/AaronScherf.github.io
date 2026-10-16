---
title: "The Resume Step That Became Faster When I Removed the AI"
summary: "Replacing a model's interpretation of a resume with a structured parser made the initial import faster and easier to check."
date: 2026-09-09
lastmod: 2026-10-16
draft: true
authors:
  - me
tags:
  - AI Projects
  - Productivity
---

The first structured import of my resume took over 90 minutes and still mixed up parts of the record. Replacing the model that organized the extracted text with ordinary parsing code brought that step down to about 1.5 seconds in the recorded run. The larger improvement was having explicit rules for where each fact belonged.

<!--more-->

The [Resume Manager](/projects/resume_manager/) is meant to help tailor applications without losing track of the experience behind them. It keeps a master record, uses a job description to guide the emphasis of a draft, and renders the result as a PDF. Before any of that can work, the master has to represent the source resume faithfully.

[[Insert Image: Create a landscape editorial illustration of a generic resume page becoming a structured master card. Connect the invented employer, role, location, and dates to four distinct fields; beside the card, show a separate editable bullet with a small wording symbol. Make the field mapping the focal point, not a speed chart. Use no real contact information or career details. Follow the image handoff's approved palette and style when available. Suggested caption: "Keep the facts in named fields before changing the emphasis." Suggested alt text: "A generic resume maps employer, role, location, and dates into separate fields, while bullet wording remains separately editable." Save an approved image as featured.jpg or featured.png in this page bundle.]]

An early version let the model write the master as free-form text. My source resume groups several roles under one employer, with a date range attached to the employer rather than every individual role. The model filled some missing date positions with locations. The result looked organized, but the meaning of a field had quietly changed.

Giving every fact a named field helped. Employer, role, location, and dates no longer had to compete for the same space in a heading. Yet asking the local model to populate that structure introduced another set of problems: malformed output, joined lines that failed literal checks, and content that still landed in the wrong place. Fixing the formatting was not enough to establish that the record was right.

The source had more regularity than the model-based approach was using. Section headings, date patterns, and the arrangement of roles supplied practical rules for a parser. The revised importer uses those rules to turn extracted PDF text into a structured master without a model call. That is the step behind the 1.5-second result; it is not the time to tailor and render a complete application, nor a benchmark across arbitrary resume layouts.

Language generation still has a useful job later. A model can suggest which experience to emphasize and how to phrase a bullet for a particular opportunity. The surrounding code copies fixed fields from the master instead of asking the model to reproduce them. Bullet wording still needs review: preserving a date or a number does not establish that every implication of a rewritten sentence is faithful.

This small project shares a concern with the academic tools: preserve a dependable source record, then make the interpretation easy to inspect. Here, the most effective change was recognizing which part of the job already had enough structure for code to do it directly.

*Retrospective draft prepared October 16, 2026, covering the September 9 milestone. The [parser change](https://github.com/AaronScherf/ai-sandbox-master/commit/467810757813902dea015abf4d1114b27a0b0d17) and [same-day run history](https://github.com/AaronScherf/ai-sandbox-master/blob/fb184576380d2e980751c08f0c26c3a1035f9860/ai-sandbox/academic-rag-model/docs/status/2026-09-09-resume-manager-status.md) document the sequence. The project page includes later developments.*
