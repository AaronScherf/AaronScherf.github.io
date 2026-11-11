---
title: reprokit
weight: 80
date: 2026-11-06
lastmod: 2026-11-10
summary: "A small framework and project template for reproducible research: documented sources, checks that catch common mistakes, and a first-run test written so a non-programmer can follow it."
image:
  caption: "Illustration: A standard project format brings source records, readable instructions, and automated checks together."
  alt_text: "A standard project format holds source descriptors, a protocol, configuration, and a README alongside automated checks for repeatable builds."
  focal_point: Center
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

A result is only worth as much as someone else's ability to get it again. reprokit is the scaffolding I use to make that possible: a fixed way to describe sources, their reuse terms, and how they were checked, plus a command that tells a newcomer whether their setup works.

<!--more-->

## The problem

Research projects usually fail to reproduce for ordinary reasons. The data source was never recorded, or its terms of use were not checked. A step depended on a file that existed only on one laptop. The instructions assumed the reader already knew what a terminal was. And when something does break, the message is written for the person who wrote the code.

I started building it while working on my [compound shocks panel](/projects/compound_shocks/), which combines several sources with different formats and rules. That project needed proof that its outputs rebuild exactly. I wanted that proof to be reusable, so the next project starts with it instead of adding it at the end.

## What I built

- **Source descriptors.** A structured record for each dataset: provider, variables and units, place and time coverage, how access works, reuse terms, and how far the data has been verified. A validator checks that the record is complete and consistent with the project's settings, and that a claim like "verified on real data" has a matching verification note.
- **Evidence projects.** A second project kind for literature and desk research keeps a source manifest and checks citations against included, verified sources. `verify-sources` checks DOI and OpenAlex identifiers online; `migrate-review` converts an older literature review into a draft manifest for screening.
- **`reprokit validate`.** One command that checks all of a project's records and prints a plain explanation for anything missing. It can also warn when a source needs an account but the README does not say how to get the data by hand.
- **`reprokit quick-check`.** A short self-test on made-up data. It reports PASS or FAIL in ordinary language, with the next command to type, and tells the reader that it does not test the real data.
- **Run summaries.** A project can write a readable file listing the rows produced, recorded time and memory per step, and checksums for its outputs, so two people can compare their results by comparing fingerprints.
- **A project template.** A repository generated with a README for non-developers (what a terminal is, what each file is for, what to do when the check fails), a protocol document, a test setup, automated checks on Linux and Windows, and a scan for accidentally committed secrets.
- **Small guards learned the hard way.** A loader for a project's `.env` file for account keys (values are never printed), and a Git setting that stops Windows from rewriting line endings in data files and silently changing their checksums.

## How well it works so far

- **It is in real use.** The compound shocks panel is built on it. Both of that project's full rebuilds, run on 2026-11-06, finished with every checksum matching the earlier recorded run. Two more projects are in progress: Bangladesh Insurance Replication and Evidence Map; neither has reported research results here.
- **Automated checks.** All 431 automated tests pass locally, and continuous integration is configured for Linux and Windows.
- **Clearer first steps.** The generated README now explains that commands go in a terminal and names the files a newcomer will meet. Windows testing found the line-ending checksum bug above, which shipped as a fix in the next release.
- **Honest limits.** The compound shocks panel is the documented real-data use so far. The memory figure in its run summary counts only the main process, so it understates heavy steps. The checks confirm that a record is complete and consistent, not that its contents are true. Older projects need a manual update to receive new template text.

Releases so far are tagged v0.1.0 through v0.4.0 on GitHub.

## What comes next

- **Try it in the two in-progress projects** and see what breaks beyond the compound shocks panel.
- **Measure memory properly** and say plainly what the number covers.
- **Make adoption easier** for an existing repository, including a clear note on how to generate a project from a local copy and how to repair line endings in older checkouts.
- **Migrate remaining records** to the current descriptor format so the stricter checks run everywhere.
- **Keep reviewing it with fresh eyes**, especially the first ten minutes for a reader who has never opened a terminal.
