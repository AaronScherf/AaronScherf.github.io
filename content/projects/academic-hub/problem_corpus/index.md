---
title: Problem Corpus Extraction
date: 2026-09-06
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/agent/problem_corpus
tags:
  - Python
  - LLM / RAG
---

Extracts a structured, persistent bank of practice problems — topic tag, problem statement, verbatim solution text if present, course, and honest provenance metadata — from course problem sets, textbooks, and recitation slides, providing the foundational dataset for practice problem generation.

<!--more-->

The **[Problem Generation Sub-Agent](/projects/academic-hub/problem_generation/)** needs real examples of course problems to anchor both difficulty and style, but course material doesn't arrive as a pre-packaged question bank. Practice problems sit embedded inside multi-page PDF problem sets, converted textbooks, and recitation slides, mixed together with headers, formatting debris, and unverified student notes. `problem_corpus` is the offline extraction tool that walks an indexed course corpus and turns those raw documents into a structured, persistent JSON bank (`<root>/.problem_corpus/<course>.json`).

A core design decision here was being honest about provenance. Inspecting the actual converted materials surfaced a crucial reality check: there is no authoritative "answer key" tier in the corpus. Converted textbook exercises have no solutions in the body text, and course problem sets either contain no answers at all or carry the student's own handwritten attempts under an explicit `### Handwritten Solutions:` heading — unverified, possibly flawed work. Rather than pretending these attempts are answer keys or having an LLM hallucinate "verified" labels, every extracted record explicitly tags `solution_provenance` as either `"student_attempt"` or `null`. Downstream agents can choose how to use or verify that text, but the data store never claims certainty it doesn't possess.

The extraction pipeline is split into clean, isolated stages:
- **Boundary Detection (`boundaries.py`)**: A pure, zero-I/O pass that scans text for numbered problem patterns (e.g. `Problem 1.2`, `Exercise 3`, `Question 4(a)`). It reuses the battle-tested problem-boundary regex logic from `core/indexer/chunk_index.py`, isolating candidate problem spans without touching the network.
- **LLM Extraction (`llm_extract.py`)**: Hands each detected span to `gemini-3.1-flash-lite` to extract the clean problem statement, isolate any accompanying solution verbatim, and assign a concise 2–3 word topic tag (e.g., "spectral theorem", "constrained optimization").
- **Incremental Persistence (`store.py` & `extractor.py`)**: Mirrors the indexer's `.index/chunks/<course>.json` shard convention. An MD5/SHA content hash keyed to each source file means a rerun only processes files that actually changed, making incremental updates practically instantaneous and free. Failure isolation operates at both file level (an unreadable file won't abort the batch) and span level (a single failed extraction doesn't discard other valid problems in that file).

Running the pipeline for real against `math-camp` validated both its extraction yield and its network resilience:
```powershell
python -m agent.problem_corpus.extractor --root ../academic-hub extract --course math-camp
```
All 8 `problem_sets` files extracted cleanly, extracting **196 genuine practice problems**. The 4 `recitation_slides` files were evaluated and correctly skipped because they lacked numbered-problem boundaries. 

The run also provided a valuable lesson in API concurrency: firing 196 extraction requests in a tight loop hit Gemini's free-tier rate limits hard (`429 RESOURCE_EXHAUSTED` on the 15 requests/minute threshold) — a pattern earlier single-query agent spikes never encountered. The retry handler in `common.gemini_utils` proved its value by parsing the API's own suggested `retryDelay` response (waiting up to ~60 seconds when requested) rather than relying on a naive blind backoff timer. Every single call eventually succeeded, achieving **196/196 problem extractions with 0 span-level failures**, finishing in several minutes for less than a cent in total compute.

Part of **Academic Hub**, bridging raw course materials indexed by **[Source Indexer](/projects/academic-hub/source_indexer/)** into the practice problem retrieval pools consumed by the **[Problem Generation Sub-Agent](/projects/academic-hub/problem_generation/)**.
