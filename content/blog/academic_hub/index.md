---
title: Introducing Academic Hub
summary: "Connecting disparate course materials to inform a searchable knowledge base."
date: 2026-08-18
lastmod: 2026-10-30
authors:
  - me
tags:
  - Academic Hub
  - LLM / RAG
  - Python
image:
  caption: "Illustration: Academic Hub brings course materials into a searchable workspace for source-linked study."
  alt_text: "Textbooks, notes, slides, problem sets, and video explainers connect to a searchable database of text files that feeds sourced answers, study guides, concept maps, and tutoring tools."
  focal_point: Center
---

Like any knowledge intensive task, taking a graduate course combines multiple sources of information in various formats: textbooks, lecture notes, presentation slides, problem sets, Youtube video explainers, old exams, and relevant research papers. The standard approach to combining these materials is haphazard, with relevant info spread across each category and only loosely connected by topic--any given section of a syllabus might connect to half a dozen textbook chapters, meaning students spend a lot of time just finding the right source. If a topic depends on pre-requisite knowledge which the student is unfamiliar with (a common issue in my PhD program so far), looking back through foundational textbooks for the right content takes longer than learning the idea. When it comes time for exam review, notes are only loosely connected to problem sets and lecture slides, and none of these are linked to practice problems or prior exams. In short, students spend far too much time categorizing and retrieving relevant information, distracting from higher value learning processes, shifting pedagogical focus from the actual ideas to the mechanics of how different authors organize and refer to those ideas.

My solution for my own coursework was the [Academic Hub](https://aaronscherf.github.io/projects/academic-hub-overview/). If all my materials could be converted to the same plain-text format, then organizing them into a searchable database with relevant categories and connections would be an easy task for any language model. As I developed methods to convert a larger variety of information sources, the potential applications for learning became more and more useful: from [notes transcription](https://aaronscherf.github.io/projects/academic-hub/notes_transcription/) that automatically answers my handwritten sidebar questions from lecture to more relevant study guides and [concept graph "mind maps"](https://aaronscherf.github.io/projects/academic-hub/concept_graph/), [study guides](https://aaronscherf.github.io/projects/academic-hub/study_guide_pipeline/) tailored to the specific topics which came up often in past exams, and even multi-round [tutoring agents](https://aaronscherf.github.io/projects/academic-hub/tutor_diagnosis/) that can help break down complex problems without revealing solutions.

<!--more-->

Most of these applications could be replicated with a standard online AI model, but the default agents lacked the context of my specific courses. Retrieval-augmented generation (RAG) models that can train on or incorporate specific files to produce more relevant answers are available, but dropping whole PDFs into a system like a Gemini Notebook is very token expensive, they waste most of their compute just processing inputs. By front-loading the transcription and indexing process, then standardizing it across my courses, I can run any type of LLM agent (subscription based, local, or API) and get highly relevant results based on my exact materials, with citations to source context, at a fraction of the cost. The more source materials I included, the more summaries and problem sets I generated, the better the collection becomes; by the end of the semester, I could just say "looking back at my previous notes and homeworks, help me review this section" and I could create much more useful review materials with far less effort.

{{< figure src="academic-hub-workflow.png" caption="Converted materials provide a shared source collection for several study tools; their outputs still need review." alt="Textbooks, notes, and slides become searchable text; a question retrieves source passages that support separate answer and study-aid drafts for review." >}}

The Academic Hub pipeline is completely reproducible too. Each step is modular, so when I found that my initial transcription approach (using Gemini API credits) was becoming too costly, I was able to switch out specific steps with a subscription-based model (or a local GPU-based model). Applying the entire range of tools to a new course is as simple as dropping in a folder of old notes, slides, and problem sets. Courses can build on each other, so if a topic from Microeconomics I comes up again in Micro II, all of my previous notes can be used to inform the new questions and help me review. Once large PDFs are converted to markdown text files, the storage requirements are minimal--I can [sync my entire notes directory](https://aaronscherf.github.io/projects/academic-hub/obsidian_git_sync/) to my tablet via GitHub and Obsidian.

While I built it to help study for courses, the processes involved can be applied to any type of knowledge base, from research papers to government reports. I've already started expanding the pipeline to academic research, to automate literature reviews and create a structured database of international development interventions and outcomes. I'm eager to expand the features for both and start applying them at a larger scale, including user testing to see if the tools are accessible to those without extensive backgrounds in computing, AI, or knowledge management.

If you have an interesting use case you'd like to try, or just want to discuss the development process, please reach out to me by email at [theaaronscherf@gmail.com](mailto:theaaronscherf@gmail.com) or [on LinkedIn](https://www.linkedin.com/in/aaron-scherf). All of the code backing up the Academic Hub is available [on GitHub](https://github.com/AaronScherf/ai-sandbox-master) as part of my larger AI-Sandbox project and each subproject has more details in the [Academic Hub overview page](https://aaronscherf.github.io/projects/academic-hub-overview/). I welcome any questions or feedback as I continue to develop this project!
