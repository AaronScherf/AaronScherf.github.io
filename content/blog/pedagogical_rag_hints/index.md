---
title: "An AI Tutor That Gives Hints and Checks Your Reasoning"
summary: "A tutor that gives hints, separates different kinds of reasoning gaps, and checks a solution with a fresh view of the problem."
date: 2026-09-29
lastmod: 2026-10-15
authors:
  - me
tags:
  - Academic Hub
  - Education
image:
  caption: 'A study tutor offering a hint, checking work, and explaining a reasoning gap'
---

An AI assistant can produce a complete solution quickly. That is not always what a student needs. When I am stuck, a useful hint can help me make progress while leaving the reasoning in my hands.

<!--more-->

I built the [Tutor Diagnosis and Hint Generator](/projects/academic-hub/tutor_diagnosis/) to support that kind of study. It uses course materials to suggest a direction, can work through a problem independently as a second check, and can compare a student's submitted reasoning with a reference explanation.

The hint feature aims to point toward a useful idea without giving away the conclusion. For a claim that is meant to hold in every case, an illustrative hint could be: "Try the simplest case you can think of. Which assumption does your argument use?" That gives me something to test while leaving the reasoning to me.

The second solver gets the question without the tutor's earlier solution or the source passages used to build it. This gives it a fresh chance to spot a missing assumption instead of following the same argument. In one recorded coursework trial, it identified a condition about the regression model that the first response had omitted.

When I share an attempt, the draft check gives separate scores for whether the conclusion is right, whether each step is justified, and whether it uses the course's definitions and methods. A correct result with a gap in the proof needs different feedback from an otherwise sound argument that uses unfamiliar notation. If the source material does not cover a point, the tutor should make that gap clear.

I still have to examine the arguments; agreement between two answers does not settle whether they are right. The [project page](/projects/academic-hub/tutor_diagnosis/) describes the recorded tests, limits, and ongoing development.
