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

A local pipeline that turns one long-form master resume into a version tailored to a specific job description — extraction, reformatting, tailoring, and fact-checking all run on a local Ollama model, with a styled PDF as the final output.

<!--more-->

The problem it's solving: a single static resume is a compromise for every job it's sent to, but hand-tailoring a new version for each application doesn't scale, and pasting a resume plus a job posting into a chatbot each time is slow and leaves no durable record of everything a resume could say. Resume Manager keeps one hand-maintained "master" Markdown file — a long-form record of every role, project, and metric — and generates a targeted version from it per application, on demand, entirely on local infrastructure.

The pipeline has two stages. A one-time bootstrap converts the existing resume PDF into that master file: local text extraction, a local-LLM reformatting pass into a consistent Markdown structure, and a bidirectional fact-preservation check against the raw extraction before anything is trusted — a clean check writes the master file directly, a flagged mismatch is set aside for manual review instead. Two real decisions came out of building this stage rather than being planned upfront. First, extraction deliberately bypasses the conversion pipeline's own tier-routing logic (reused elsewhere in Academic Hub for notes and journal articles): that logic sniffs a PDF's metadata to decide whether a document is "clean" enough for free local extraction, and the actual resume PDF's metadata (`Skia/PDF`, a headless-Chrome export) isn't on its recognized list — which would have silently routed a perfectly typeset resume through the same expensive, vision-model fallback built for handwritten scans. Second, PDF rendering swapped from `weasyprint` to `xhtml2pdf` after `weasyprint` turned out to need native Pango/GTK libraries that aren't a plain `pip install` on Windows; `xhtml2pdf` is pure Python and renders the same styled layout. Per-application tailoring then runs a local Ollama call against the master resume and a job description, an automated fact-diff check flags (without ever blocking) anything in the result that doesn't trace back to the master, and the tailored Markdown is rendered to a submission-ready PDF.

Work in progress: the pipeline is fully built and tested, but hasn't yet been run against the real resume or used to generate a real tailored application — that first real pass, plus tuning the fact-diff checks against real content, is next.
