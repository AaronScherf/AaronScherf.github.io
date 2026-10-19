---
title: "A Long Study Guide Still Needs to Answer the Right Questions"
summary: "The first microeconomics guide connected selected sources, drafting, and reviewed edits—and showed why the finished guide still needed checking against the assignment."
date: 2026-10-09
lastmod: 2026-10-19
draft: false
image:
  caption: "An illustration of checking guide coverage against the assignment."
  alt_text: "An illustrative assignment checklist matches two study-guide sections while a third requirement reveals a coverage gap, despite a reviewed edit elsewhere."
  focal_point: Center
authors:
  - me
tags:
  - Academic Hub
  - Study Guides
---

The first microeconomics run of my study-guide pipeline produced eleven topics of explanations, but missed material needed for one of the assignment questions. It also imported language about statistical tests from an earlier econometrics prompt. A guide can be substantial, well organized, and still leave the reader unprepared for the problem in front of them.

<!--more-->

There was a useful advance here as well. The [Study Guide Pipeline](/projects/academic-hub/study_guide_pipeline/) could now assemble a guide from an explicit source plan, expand a chosen topic, and propose revisions for review. I could inspect what it planned to read and decide which edits to keep, instead of asking for a complete rewrite and trying to spot everything that had changed.

That source plan connects the visible study aid to the less visible infrastructure. The [conversion tools](/projects/academic-hub/marker_conversion/) prepare textbooks and course notes; the [Source Indexer](/projects/academic-hub/source_indexer/) locates passages within them. For a guide, I can name particular sources and sections as well as request a bounded search. Newly discovered passages normally wait for review before drafting.

Revision works on specific changes. It can suggest removing an irrelevant passage, consolidating repeated explanations, correcting a claim, or reorganizing a section. Applying accepted edits creates a revised copy and checks that untouched blocks remain unchanged. It also refuses a review if the guide has changed since the review was prepared. Those checks make edits traceable; mathematical judgment still has to come from examining the content.

The microeconomics run made that distinction concrete. Its audit identified several real issues, but some were recorded as notes rather than supplied with corrections. Accepting a warning did not repair the underlying argument. A later comparison with the assignment found additional errors, including a worked example whose construction could not demonstrate what it claimed. Missing coverage had to be written by hand and checked numerically.

The finished guide became usable through that combination of generated material, reviewed changes, and hand repairs. It also exposed a generalization problem: a prompt built around one statistical topic had carried assumptions into another subject. A more neutral prompt and course-specific relevance settings were follow-up work at this point.

The practical payoff is a guide I can investigate. If a topic is thin, I can examine the source plan. If a paragraph changes, I can inspect the proposed edit. If the guide is meant to prepare me for an assignment, that assignment supplies a final coverage check. Each makes the next revision more focused than simply asking the model for a better guide.

*Retrospective account prepared October 16, 2026, covering the October 9 milestone. The [dated microeconomics run record](https://github.com/AaronScherf/ai-sandbox-master/blob/bbcf843bac181794e37c47772fe82ff57ac97b54/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-09-microecon-hw4-guide-status.md) and [pipeline instructions at the same revision](https://github.com/AaronScherf/ai-sandbox-master/blob/bbcf843bac181794e37c47772fe82ff57ac97b54/ai-sandbox/academic-rag-model/agent/study_guide/README.md) distinguish implemented steps from proposed improvements. Project links include later developments.*
