---
title: Introducing Academic Hub
summary: An overview of Academic Hub — the knowledge ecosystem I'm building to unify my textbooks, notes, and research — plus progress on its Marker PDF Conversion and RAG Analysis subprojects.
date: 2026-08-18
authors:
  - me
tags:
  - Academic Hub
  - LLM / RAG
  - Python
---

For the past few months I've been building **Academic Hub**: an attempt to turn everything I read and write as a PhD student — textbooks, lecture notes, problem sets, old exams, journal articles, and my own research — into a single, AI-queryable knowledge ecosystem, instead of a pile of PDFs scattered across Drive, Paperpile, and a dozen local folders.

<!--more-->

The [full architecture is now public on GitHub](https://github.com/AaronScherf/ai-sandbox-master). It's an orchestrator repository that scaffolds and syncs a containerized workspace across three domains: a Git-managed code ecosystem (this website, research project repos, conversion scripts), an Rclone-managed data ecosystem (raw textbooks and handwritten notes mirrored to Google Drive, kept out of version control), and a Docker sandbox where an AI assistant can work across both without ever touching credentials directly — API keys live in a git-ignored `.env` file, referenced by variable from the tracked `docker-compose.yml`. A single `workspace_generator.sh` script bootstraps the whole tree, pulls updates across every nested repo, and regenerates the documentation, all without ever overwriting existing files.

Two subprojects are furthest along:

- **[Marker PDF Conversion](/projects/academic-hub/marker_conversion/)** is up and running: it spins up a temporary GPU virtual machine in Google Cloud, batch-converts dense textbook PDFs into clean Markdown with LaTeX-rendered formulae and separated figures, and tears the VM down as soon as it's finished to keep costs low.
- **[RAG Analysis](/projects/academic-hub/rag_analysis/)** is still in the design stage. It's meant to be the piece that actually reads the Markdown Marker produces — answering direct questions and acting as a retrieval step other agents can call into — but the retrieval pipeline itself isn't built yet.

The rest of the ecosystem — the academic-hub folder structure, secure secrets handling, and keeping every nested project a clean, independently pushable Git repo — is mostly scaffolding at this point, but it's the foundation everything else builds on. More to come as the RAG piece takes shape.
