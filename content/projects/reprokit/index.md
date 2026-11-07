---
title: reprokit
weight: 80
date: 2026-11-06
lastmod: 2026-11-06
summary: "A small framework and project template for reproducible research: documented data sources, checks that catch common mistakes, and a first-run test written so a non-programmer can follow it."
image:
  caption: "Illustration: A project template and a handful of checks turn a research folder into something a newcomer can verify in one minute."
  alt_text: "A project folder passes through three checks (validate, quick check, run summary) and ends with matching checksums that two people can compare."
# TODO(image): featured.png not generated yet. Gemini brief for a later run (1376 x 768 PNG, same visual style as the other
# content/projects/*/featured.png illustrations; save as content/projects/reprokit/featured.png):
#   Left, a project folder icon labelled "Research project" containing small file tiles: "Source descriptors", "Protocol",
#   "Config", "README for newcomers".
#   Centre, three short stages in a row connected by arrows, each a labelled box: "validate" (a checklist with a warning
#   triangle on one line), "quick check" (a small test tube or stopwatch with "PASS" in plain words, caption "made-up data,
#   under a minute"), "run summary" (a page showing rows, time, memory and a short fingerprint string).
#   Right, two laptops (one Windows, one Mac or Linux style, drawn generically) each showing the same fingerprint, joined
#   by an equals sign, with the label "same checksums".
#   Along the bottom, a thin strip of two small badges: "Linux + Windows tests" and "secret scan".
#   Must not include: real code, terminal screenshots, logos, real file hashes (use an obviously fake string such as
#   "a3f9...c21"), or any claim about results beyond "checksums match". Plain light background, readable labels, no dense
#   paragraphs of text.
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/reprokit
  - type: site
    icon: brands/github
    label: 'Status: Compound Shocks and reprokit'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/compound_shocks/2026-11-06-reprokit-and-panel-status.md
tags:
  - Python
  - Reproducibility
  - Research tooling
---

A result is only worth as much as someone else's ability to get it again. reprokit is the scaffolding I use to make that possible: a fixed way to describe where data came from, what it is allowed to be used for, and how it was checked, plus a command that tells a newcomer in under a minute whether their setup works.

<!--more-->

## The problem

Research projects usually fail to reproduce for ordinary reasons. The data source was never recorded, or its terms of use were not checked. A step depended on a file that existed only on one laptop. The instructions assumed the reader already knew what a terminal was. And when something does break, the message is written for the person who wrote the code.

I started building it while working on my [compound shocks panel](/projects/compound_shocks/), which combines several sources with different formats and rules. That project needed proof that its outputs rebuild exactly. I wanted that proof to be reusable, so the next project starts with it instead of adding it at the end.

## What I built

- **Source descriptors.** A structured record for each dataset: provider, variables and units, place and time coverage, how access works, reuse terms, and how far the data has been verified. A validator checks that the record is complete and consistent with the project's settings, and that a claim like "verified on real data" has the evidence it needs.
- **`reprokit validate`.** One command that checks all of a project's records and prints a plain explanation for anything missing. It can also warn when a source needs an account but the README does not say how to get the data by hand.
- **`reprokit quick-check`.** A short self-test on made-up data. It reports PASS or FAIL in ordinary language, with the next command to type, and tells the reader that it does not test the real data.
- **Run summaries.** Each run writes a readable file listing the rows produced, time and memory per step, and a checksum for every output, so two people can compare their results by comparing fingerprints.
- **A project template.** A repository generated with a README for non-developers (what a terminal is, what each file is for, what to do when the check fails), a protocol document, a test setup, automated checks on Linux and Windows, and a scan for accidentally committed secrets.
- **Small guards learned the hard way.** A loader for a project's `.env` file for account keys (values are never printed), and a Git setting that stops Windows from rewriting line endings in data files and silently changing their checksums.

## How well it works so far

- **It is in real use.** The compound shocks panel is built on it. Both of that project's full rebuilds, run on 2026-11-06, finished with every checksum matching the earlier recorded run.
- **Tested on both major systems.** 131 automated tests pass, and continuous integration runs on Linux and Windows. A project generated fresh from the current release, in a scratch repository, passed all three automated jobs, including the secret scan.
- **It improved when tried by someone new.** A walk-through as a non-developer found that the first README never said the quoted commands were meant for a terminal and left some file names unexplained. I rewrote it, and I keep that kind of review as part of each release. Windows testing found the line-ending checksum bug above, which shipped as a fix in the next release.
- **Honest limits.** It has been used on one real project so far. The memory figure in the run summary counts only the main process, so it understates heavy steps. The checks confirm that a record is complete and consistent, not that its contents are true. Older projects need a manual update to receive new template text.

Releases so far are tagged v0.1.0 through v0.3.2 on GitHub.

## What comes next

- **Use it on a second project** and see what breaks, since one example is a weak test.
- **Measure memory properly** and say plainly what the number covers.
- **Make adoption easier** for an existing repository, including a clear note on how to generate a project from a local copy and how to repair line endings in older checkouts.
- **Migrate remaining records** to the current descriptor format so the stricter checks run everywhere.
- **Keep reviewing it with fresh eyes**, especially the first ten minutes for a reader who has never opened a terminal.
