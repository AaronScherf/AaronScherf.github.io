---
title: "An AI Tutor That Gives Hints and Checks Your Reasoning"
summary: "A tutor that gives hints, separates different kinds of reasoning gaps, and checks a solution with a fresh view of the problem."
date: 2026-09-29
lastmod: 2026-10-16
authors:
  - me
tags:
  - Academic Hub
  - Education
image:
  caption: 'Illustration: A tutor gives a hint and reviews a student attempt.'
  alt_text: 'A student question branches into a tutor hint, while a separate student attempt leads to a review of reasoning and course alignment.'
---

An AI assistant can produce a complete solution quickly. That is not always what a student needs. When I am stuck, a useful hint can help me make progress while leaving the reasoning in my hands.

<!--more-->

I built the [Tutor Diagnosis and Hint Generator](/projects/academic-hub/tutor_diagnosis/) to support that kind of study. It uses course materials to suggest a direction and can compare a student's reasoning with a reference explanation. For a second check, a separate solver gets the question without the tutor's earlier answer or the source passages used to build it.

The hint feature aims to point toward a useful idea without giving away the conclusion. For a claim that is meant to hold in every case, an illustrative hint could be: "Try the simplest case you can think of. Which assumption does your argument use?" That gives me something to test while leaving the reasoning to me.

That fresh view gives the second solver a chance to spot a missing assumption instead of following the same argument. In one recorded coursework trial, it identified a condition about the regression model that the first response had omitted.

When I share an attempt, the draft check gives separate scores for whether the conclusion is right, whether each step is justified, and whether it uses the course's definitions and methods. A correct result with a gap in the proof needs different feedback from an otherwise sound argument that uses unfamiliar notation. If the source material does not cover a point, the tutor should make that gap clear.

I still have to examine the arguments; agreement between two answers does not settle whether they are right. The [project page](/projects/academic-hub/tutor_diagnosis/) describes the recorded tests, limits, and ongoing development.
