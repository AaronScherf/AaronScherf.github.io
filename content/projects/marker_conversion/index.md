---
title: Marker PDF Conversion
date: 2026-08-19
links:
  - type: site
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/marker-conversion
tags:
  - Python
  - Google Cloud Platform
  - LLM / RAG
---

A cost-optimized pipeline that runs the open-source Marker model on a temporary GPU virtual machine in Google Cloud to convert dense, math- and figure-heavy textbook PDFs into clean, LLM-ready Markdown — with formulae, tables, and figures cleanly separated for downstream use.

<!--more-->

A small local tool drives the whole process: it spins up a GPU virtual machine in Google Cloud, uploads a batch of textbook PDFs, and converts them all in one pass, reusing the same loaded model across every book to keep runtime and cost down. Along the way, an optional AI-assisted step reads each book's title page to automatically label the output files with the correct title, author, and year.

The converted Markdown and extracted images are copied back locally, and the cloud VM is shut down right after to avoid idle billing — so a full shelf of textbooks can be processed in a single, low-cost session.

The output feeds **Academic Hub**, a broader project that synthesizes textbooks, lecture notes, problem sets, exams, journal articles, and original research into a unified knowledge network powering AI assistants tuned to specific academic domains. The same approach generalizes to any dense PDF archive that needs to become queryable by an LLM or RAG system.
