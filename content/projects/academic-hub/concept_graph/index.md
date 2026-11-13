---
title: "Concept Graph"
summary: "Explore two interactive maps that show how course ideas connect, what those connections depend on, and where to check them in the source material."
date: 2026-10-11
lastmod: 2026-11-13
draft: false
type: academic-hub-project
links:
  - type: site
    icon: globe
    label: Try the microeconomics graph
    url: https://aaronscherf.github.io/microecon-concept-graph/
  - type: site
    icon: globe
    label: Try the econometrics graph
    url: https://aaronscherf.github.io/econometrics-concept-graph-site/
tags:
  - Learning Tools
image:
  caption: "The interactive microeconomics concept graph, with a selected idea and its connections."
  alt_text: "An interactive map of microeconomics concepts connected by lines, with details for a selected concept."
  focal_point: Center
params:
  subproject:
    id: concept_graph
    package: agent/concept_graph
    code_paths:
      - ai-sandbox/academic-rag-model/agent/concept_graph
    readme_path: ai-sandbox/academic-rag-model/agent/concept_graph/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-09-concept-graph-core-status.md
        role: historical
        lifecycle_ids:
          - concept-graph-core
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-10-concept-graph-pipeline-status.md
        role: historical
        lifecycle_ids:
          - concept-graph-pipeline
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-14-concept-graph-proposals-status.md
        role: historical
        lifecycle_ids:
          - concept-graph-proposals
          - concept-graph-viewer
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-15-concept-graph-status.md
        role: historical
        lifecycle_ids:
          - concept-graph-proposals
          - concept-graph-viewer
      - path: ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-21-econometrics-second-course-status.md
        role: current
        lifecycle_ids:
          - concept-graph-proposals
          - concept-graph-viewer
    members: []
---

When learning a new subject, we often focus more on the individual concepts rather than how they fit together. To help connect the dots, I built an interactive concept map based on my course notes. It lets me explore the relationships between topics in a spatial way, rather than just reviewing lecture slides or long-form notes. Each topic box is an idea from a course, while each connection explains how one idea relates to another. Some connections also spell out a condition that must be true before the relationship holds, to understand dependency relationships. The topic nodes and connections all reference directly the source material used to build it, to validate the information and in case I want to investigate further.

**Try the live maps:**

- [Explore the microeconomics concept graph](https://aaronscherf.github.io/microecon-concept-graph/) — follow ideas through a graduate microeconomic theory course.
- [Explore the econometrics concept graph](https://aaronscherf.github.io/econometrics-concept-graph-site/) — see how concepts, methods, and assumptions connect in a graduate econometrics course.

Click an idea to read its explanation and see its connections. Click a connection to read what it claims and the condition, if any, that makes it work. If the full map feels crowded, choose a course section to focus on one part at a time.

I started building these as a study tool, but quickly found that the format is useful for breaking down any large body of information into related themes. I built out an interactive web app using Claude to host the graphs on Github, so that my fellow students could explore them and suggest revisions to the maps or propose new concepts. I hope to expand these to not just other academic courses, but as a broader tool for mapping out complex domains of knowledge.

<!--more-->

## A map for studying, not just browsing

The graph is useful when a new topic or theorem is introduced but it isn't immediately clear how it connects to the rest of the course. I can trace any concept back through the definitions and assumptions it needs, then follow those ideas to see what else they support. In econometrics, for instance, an estimate can depend on assumptions about the data. Seeing those assumptions as distinct ideas makes it easier to ask what might change if one does not hold.

The connections matter as much as the concepts. Two terms placed near each other might look related, but proximity does not tell me *how* they are related. A line that says “this result follows when this condition holds” gives me something I can examine, question, and check against the source. These connector arrows are not only useful for visually "connecting the dots", when clicked they pull up a longer description explaining exactly how the concepts are related.

## Beyond a single course

The same approach could help organize any collection of ideas where relationships matter: a research topic, a set of policy arguments, or a systems map. As long as there are machine readable source documents, this open-source pipeline can produce a concept map using the same infrastructure. So far, I have built live examples for two courses; I hope to keep expanding them as these courses progress, build out examples for new academic disciplines, and see if the approach can be useful for other knowledge domains outside of the classroom.

If you have an interesting idea for how to apply a concept map to a collection of documents or data, please reach out to me via [LinkedIn](https://www.linkedin.com/in/aaron-scherf) or [by email](mailto:theaaronscherf@gmail.com)!

## How I built it, and what surprised me

The maps grow out of my [Academic Hub](https://aaronscherf.github.io/projects/academic-hub-overview/), where I bring together lecture notes, slides, assignments, and textbooks. [Notes Transcription](https://aaronscherf.github.io/projects/academic-hub/notes_transcription/) and [Textbook Conversion](https://aaronscherf.github.io/projects/academic-hub/marker_conversion/) make those materials searchable; the [Source Indexer](https://aaronscherf.github.io/projects/academic-hub/source_indexer/) helps find the passages behind a proposed connection. The same collection also supports my [Study Guide Pipeline](https://aaronscherf.github.io/projects/academic-hub/study_guide_pipeline/), which generates longer form explanations for a specific set of topics.

I used several AI tools and coding pipelines to help read that collection, suggest the ideas and connections worth mapping, and build the interactive web interface. By leveraging my existing corpus of course materials, I was able to ground the initial AI drafts for concepts and connections in the terminology and notation of my own class. With targeted human-in-the-loop review and adversarial agent critique of selected samples, I validated the accuracy of the information against the source files (which stay linked to the summarized claims), then compared the final product with my overall syllabus and lecture notes to confirm it was comprehensive.

Building a second map taught me that a plausible looking draft can still miss important material. The first econometrics pass omitted an entire topic from the syllabus. Comparing the map with the assigned readings revealed the gap and led to more concepts. It also showed me that different subjects need different kinds of connections: a condition required for an estimate is not quite the same as a premise in a mathematical proof.

Another lesson was to make the map inspectable. A source reference helps me check a claim, but it does not guarantee the claim is right; an AI tool can misunderstand a passage. At the latest documented checkpoints, the concepts and connections in both maps were still proposals awaiting human review. Rather than validate the entire knowledge map myself, I built one more tool to let others review the information in a collaborative way.

Anyone viewing the concept graph website can suggest a missing concept, propose a new connection, or comment on something already in the map. The **Submit review** button opens a prepared GitHub issue, which works like an online suggestion form; making the system easier for those without a GitHub account is a work in progress. Then, I can review the submissions (or have another agent go through them first), resolve any conflicting suggestions, and update the published map after deciding which changes to accept. The concept map becomes a living knowledge web that a whole class or team can add to over time!
