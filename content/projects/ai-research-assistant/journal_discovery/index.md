---
title: Journal Discovery Pipeline
date: 2026-09-02
type: ai-research-assistant-project
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model
tags:
  - Python
  - Hugging Face
  - LLM / RAG
---

The layer that decides what actually gets fed into **[Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/)** in the first place — resolves a faculty name or research topic into full-text PDFs automatically, via OpenAlex and a chain of open-access sources, with a manual-download fallback and a click-through worklist for whatever a script genuinely can't reach on its own.

<!--more-->

Two ways in: a faculty name (`--faculty "Daniel Björkegren"`) or a free-text topic (`--topic "climate shock adaptation"`), either repeatable and combinable in one run. Every candidate OpenAlex returns is scored locally first — a `sentence-transformers` embedding of a `--relevance-prompt` you write, compared against each candidate's own abstract — before any network access is even attempted, so a `--relevance-threshold` and a `--max-results` ceiling bound both the *quality* and the *volume* of what gets pulled, entirely offline and at zero LLM API cost. A live faculty-seeded run found and scored one applied economist's entire relevant OpenAlex-indexed output this way: 19 genuine papers surfaced above threshold, no manual trawling of his publication list required.

A third route grows the corpus organically instead of searching from scratch: citation-based snowball sampling follows OpenAlex's own "cited by" graph forward from whatever's already been fetched, no bibliography text-parsing needed. It's deliberately two steps, never auto-fetching anything — `snowball propose` finds and scores what cites the corpus's existing papers, writing a checkbox worklist (`snowball_candidates.md`) with each candidate's relevance score and which corpus paper it cites; `snowball confirm` then fetches full text only for whatever got checked, through the identical access chain below. Nothing is downloaded on the strength of a citation graph alone — a human always reviews the proposed list first.

Full-text access then tries four tiers in order — Unpaywall, then Semantic Scholar, then arXiv, then Columbia's own EZProxy for anything still gated — each a real, free API except the last, which needs a manually-supplied session cookie and paces its own request rate specifically to protect the account behind it, not just out of politeness to the host. Whatever can't be resolved automatically doesn't get guessed at or silently dropped: it lands in a generated, click-through `needs_manual_downloads.md`, each entry linking straight to the paper's DOI and naming the exact auto-created topic folder to save it into. A separate reconciliation pass — run once some manual downloading and conversion has happened — confirms which papers actually landed by searching the *converted text itself* for a DOI or title match, since a manually-saved PDF's filename never resembles anything the pipeline would have generated on its own, and drops confirmed entries off the list automatically.

The most interesting real result here wasn't a bug: authenticating live through Columbia's EZProxy and then requesting a Taylor & Francis and an Elsevier article directly showed that institutional access was never actually the obstacle — both got blocked at the publisher's own Cloudflare layer, which fingerprints a scripted client's TLS handshake and missing JS execution regardless of whether a valid session cookie is attached. A perfectly fresh cookie hits the identical wall. Deliberately left unworked-around: spoofing a browser's fingerprint or replaying Cloudflare's own clearance cookie crosses from "fetching content already licensed" into defeating a publisher's anti-bot system outright, a different thing entirely from the pacing this pipeline does elsewhere to protect its own account. The real workaround is the manual-download path above, and it carries genuine load in practice — one full batch against an economist's real output landed only 3 of 19 genuine papers automatically, the rest needing a human's own authenticated browser. Two smaller, more mundane rough edges round this out: OpenAlex's own concept tags are occasionally homonym-prone (a paper about market competition briefly filed itself under "Competition (biology)," fixed by preferring a broader top-level concept whenever one is present) and occasionally just wrong (two papers turned out to belong to a different, similarly-named researcher merged into the same author record) — external metadata quality this pipeline can flag but not fully correct for.

CORE.ac.uk and Columbia's own Academic Commons repository are two more free, real APIs worth adding as open-access tiers ahead of EZProxy; a semi-automated login through a genuine browser (not a spoofed one) remains the honest next step if manual-download volume ever becomes the real bottleneck. Part of the same **[Source Indexer](/projects/academic-hub/source_indexer/)** / **[RAG Analysis](/projects/academic-hub/rag_analysis/)** ecosystem the rest of **AI Research Assistant** builds on, feeding **[Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/)** directly.
