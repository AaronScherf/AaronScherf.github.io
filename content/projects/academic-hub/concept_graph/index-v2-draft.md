---
title: "Concept Graph (Version 2 Draft)"
summary: "Explore two interactive maps that show how course ideas connect, what those connections depend on, and where to check them in the source material."
date: 2026-10-11
lastmod: 2026-11-13
draft: true
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
---

When I study a difficult subject, I often understand the individual ideas before I understand how they fit together. A concept graph gives me a way to explore those relationships. Each point is an idea from a course; each connection explains how one idea relates to another. Some connections also spell out a condition that must be true before the relationship holds. I can follow a line back to the course material behind it, rather than taking the map's word for it.

**Try the live maps:**

- [Explore the microeconomics concept graph](https://aaronscherf.github.io/microecon-concept-graph/) — follow ideas through a graduate microeconomic theory course.
- [Explore the econometrics concept graph](https://aaronscherf.github.io/econometrics-concept-graph-site/) — see how concepts, methods, and assumptions connect in a graduate econometrics course.

Click an idea to read its explanation and see its connections. Click a connection to read what it claims and the condition, if any, that makes it work. If the full map feels crowded, choose a course section to focus on one part at a time.

<!--more-->

## A map for studying, not just browsing

The graph is useful when a result feels like it appeared from nowhere. I can trace it back through the definitions and assumptions it needs, then follow those ideas to see what else they support. In econometrics, for instance, an estimate can depend on assumptions about the data. Seeing those assumptions as distinct ideas makes it easier to ask what might change if one does not hold.

The connections matter as much as the concepts. Two terms placed near each other might look related, but proximity does not tell me *how* they are related. A line that says “this result follows when this condition holds” gives me something I can examine, question, and check against the source.

## Beyond a single course

The same approach could help organize any collection of ideas where relationships matter: a research field, a set of policy arguments, or even the knowledge needed for a new job. A useful map would show which ideas define others, which claims depend on assumptions, and which sources support each connection. So far, I have built live examples for two courses; applying the approach elsewhere is a possibility to explore, not a result I have established.

## How I built it, and what surprised me

The maps grow out of my [Academic Hub](/projects/academic-hub-overview/), where I bring together lecture notes, slides, assignments, and textbooks. I used AI tools to help read that collection, suggest the ideas and connections worth mapping, and build the interactive web interface. The AI supplied drafts; I guided the process, compared its coverage with course materials, and built in a way for people to review the results.

Building a second map taught me that a plausible looking draft can still miss important material. The first econometrics pass omitted an entire topic from the syllabus. Comparing the map with the assigned readings revealed the gap and led to more concepts. It also showed me that different subjects need different kinds of connections: a condition required for an estimate is not quite the same as a premise in a mathematical proof.

Another lesson was to make the map inspectable. A source reference helps me check a claim, but it does not guarantee the claim is right; an AI tool can misunderstand a passage. At the latest documented checkpoints, the concepts and connections in both maps were still proposals awaiting human review. I hope the maps are useful places to start exploring and asking better questions. I have not measured whether studying with them improves learning.
