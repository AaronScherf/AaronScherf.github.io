---
title: Resume Manager
date: 2026-09-09
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/resume_manager
tags:
  - Python
  - LLM / RAG
---

A local pipeline that turns one long-form master resume into a version tailored to a specific job description — structured extraction, selective rewriting, and fact-checking, with a styled PDF as the final output. Three real design revisions in one day, each driven by a bug found running it against my actual resume, landed on a surprising conclusion: the harder of the pipeline's two stages didn't need a local LLM at all.

<!--more-->

The problem it's solving: a single static resume is a compromise for every job it's sent to, but hand-tailoring a new version for each application doesn't scale, and pasting a resume plus a job posting into a chatbot each time is slow and leaves no durable record of everything a resume could say. Resume Manager keeps one hand-maintained master file — a long-form record of every role, project, and metric — and generates a targeted version from it per application, on demand, entirely on local infrastructure.

The master started as freeform Markdown authored by a local LLM reformatting pass. Against my real resume, that fell over in an instructive way: three sequential roles at one employer share a single printed date range, and with only one freeform `(dates)` slot per entry, the model silently substituted a role's *location* into that slot instead of leaving it honestly blank. The fix was structural — a real YAML schema with a named field for every piece of data — but getting *that* extraction reliable took five more rounds of real, evidence-driven fixes (an LLM occasionally writing a bare `-` as a "no value" placeholder that isn't valid YAML at that position; a genuine venue name containing its own colon breaking YAML's mapping syntax; whitespace and zero-width-space artifacts in the source PDF making faithfully-normalized bullets look "invented" to a naive fact-check) — and even after all of that, a real job still got miscategorized into the wrong section with its bullets dropped entirely, and a real thesis title got written off as "not specified" even though it was sitting right there in the extracted text. Every one of these traced back to the same root cause: a machine-generated, cleanly-sectioned resume doesn't need an LLM to decide where content belongs — it needs a parser that recognizes the shape it's already in. Swapping the entire bootstrap extraction step for deterministic, section-aware parsing (fuzzy-matched headers, a handful of fixed per-entry line shapes) fixed every one of those bugs at once and dropped bootstrap runtime from over 90 minutes of CPU-only inference to about a second and a half, with zero API calls.

Per-application tailoring still uses a local Ollama model — rewriting bullets to match a job description's vocabulary is a genuine language task — but it's scoped narrowly: the model only ever sees an entry's id, org, role, and existing bullets, and returns only which entries to keep and rewritten bullet text. My own code, not the model, reconstructs the final resume from the master data, so a date, an employer name, or a location can't be fabricated during tailoring — there's no field left in the model's response to put a wrong value into. Run for real against an actual UN economist job posting, this caught its own real gap: a bidirectional fact-check (checking for content quietly dropped, not just content invented) flagged a dollar figure that vanished when three bullets got compressed into two, and manual review of the same output found a repeated opening phrase across two different bullets, and a couple of merged bullets that lost a named award along the way.

Work in progress. Real use surfaced a clear next list: rendering a genuinely-missing field as blank instead of printing "Not specified" literally, fitting the tailored output to a page limit, reducing repeated phrasing across bullets, a paired cover-letter generator, and — the one I'm most curious about — a brainstorming-style back-and-forth where I answer a few questions about the job before the model chooses what to emphasize, rather than it inferring my intent from the posting alone.
