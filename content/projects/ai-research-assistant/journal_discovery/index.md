---
title: Journal Discovery Pipeline
date: 2026-09-02
type: ai-research-assistant-project
image:
  caption: 'Journal discovery system architecture from OpenAlex query and relevance scoring to 5-tier download waterfall'
  image_suggestion: "Flowchart diagram illustrating the Journal Discovery pipeline: showing faculty/topic input and snowball citation expansion via OpenAlex, offline sentence-transformers semantic relevance scoring, the five-tier full-text access chain (Unpaywall -> Semantic Scholar -> CORE -> arXiv -> EZProxy), and the human-in-the-loop manual download worklist."
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

The discovery step for **[Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/)**: it finds papers related to a person or topic, checks open-access sources, and leaves other papers for the researcher to access through their library.

**In plain language:** This tool helps find papers related to a research topic and organize papers you can access into a searchable library.

<!--more-->

*Figure: Journal Discovery system architecture from OpenAlex query and semantic relevance scoring to the 5-tier full-text download waterfall and manual download fallback.*

Two ways in: a faculty name (`--faculty "Daniel Björkegren"`) or a free-text topic (`--topic "climate shock adaptation"`), either repeatable and combinable in one run. Every candidate OpenAlex returns is scored locally first — a `sentence-transformers` embedding of a `--relevance-prompt` you write, compared against each candidate's own abstract — before any network access is even attempted, so a `--relevance-threshold` and a `--max-results` ceiling bound both the *quality* and the *volume* of what gets pulled, entirely offline and at zero LLM API cost. A live faculty-seeded run found and scored one applied economist's entire relevant OpenAlex-indexed output this way: 19 genuine papers surfaced above threshold, no manual trawling of his publication list required.

A third route grows the corpus organically instead of searching from scratch: citation-based snowball sampling follows OpenAlex's own "cited by" graph forward from whatever's already been fetched, no bibliography text-parsing needed. It's deliberately two steps, never auto-fetching anything — `snowball propose` finds and scores what cites the corpus's existing papers, writing a checkbox worklist (`snowball_candidates.md`) with each candidate's relevance score and which corpus paper it cites; `snowball confirm` then fetches full text only for whatever got checked, through the identical access chain below. Nothing is downloaded on the strength of a citation graph alone — a human always reviews the proposed list first. The first live run of this route caught a real design flaw fast: candidates with no abstract to score (common for closed-access publishers that don't share one at all) were being admitted as blind fillers regardless of relevance, and one heavily-cited but off-topic seed paper flooded the worklist with over 40 irrelevant candidates before the fix landed — replaced with title-based scoring through the same relevance threshold everything else uses, explicitly flagged as a lower-confidence signal whenever abstract text isn't available.

Full-text access then tries five tiers in order — Unpaywall, then Semantic Scholar, then CORE.ac.uk, then arXiv, then Columbia's own EZProxy for anything still gated — each a real, free API except the last, which needs a manually-supplied session cookie and paces its own request rate specifically to protect the account behind it, not just out of politeness to the host. Whatever can't be resolved automatically doesn't get guessed at or silently dropped: it lands in a generated, click-through `needs_manual_downloads.md`, each entry linking straight to the paper's DOI and naming the exact auto-created topic folder to save it into. A separate reconciliation pass — run once some manual downloading and conversion has happened — confirms which papers actually landed by searching the *converted text itself* for a DOI or title match, since a manually-saved PDF's filename never resembles anything the pipeline would have generated on its own, and drops confirmed entries off the list automatically.

## Testing

A live trial of 19 relevant papers retrieved 3 automatically through the tested sources. Other papers needed the researcher to open the publisher link in a normal authenticated browser. Some publishers returned access challenges to scripted requests, even when the institutional session was valid. The pipeline stops at that boundary and does not spoof browser fingerprints, replay challenge cookies, or attempt to defeat access controls.

Other tests found limits in external metadata: subject tags can be ambiguous, and author records can combine similarly named researchers. The pipeline can flag such cases, but metadata providers remain the source of those errors.

The access route for institutional subscriptions remains limited. If a scripted request is denied, the supported next step is user-led access through the institution's ordinary browser session. Any future automation here would need to use an authorized, supported route; bypassing publisher controls is out of scope.

## Ongoing Development

A gap stayed open even after all of the above worked: a `.meta.json` sidecar is written once, from OpenAlex data, before the full text even exists — nothing ever checked it, or the folder a paper landed in, against what the paper actually turned out to say once converted. A new automatic pass closes it, chained onto the end of the reconciliation step above rather than left as a separate command to remember, since it costs nothing beyond one free OpenAlex lookup per paper. Folder placement and tag-frontmatter sync get corrected outright, since both have a mechanically derivable right answer; a title or author list that no longer matches the converted text gets flagged into a worklist for a human instead, since there's no safe automatic replacement for either. The first live run against the real corpus caught two more real bugs before it could be trusted: a missing `.env`-loading call meant the whole thing silently no-opped despite valid credentials, and a DOI-presence check flagged 14 of 17 real papers as mismatched — root-caused by reading one flagged paper's actual text directly, which showed its own DOI never appears in its body at all, only *other* papers' DOIs, in its reference list. Real academic papers routinely don't self-print their own DOI; the check was removed rather than patched, since no reliable identity signal was going to come from data that's usually just absent. A clean re-run after both fixes: 17 papers checked, 0 folder corrections needed, 0 tag syncs needed, 0 flags — a genuinely clean corpus, not an audit that found nothing because it was broken.

A fourth open-access service, CORE, was added after a live API test. Two open-access files were retrieved using its documented API download route and a standard User-Agent header. This result applies to CORE-hosted files only; it does not provide a way around publisher access challenges.

One real gap surfaced only once converted papers were checked directly, not designed for up front: the transcription prompt says nothing about how to handle charts or plots, so a data table converts losslessly but a scatter plot or time series gets only a bracketed caption — axis labels and variable names, no underlying values. Most quantitative results in these papers also show up in a table or in-text statistic, so the loss is real but partial; left open rather than fixed, and marked as the next thing to solve once the discovery-tier work above settles, per direct user decision.

The current next step is to keep the user-led handoff clear and reliable; any more automation for institutional access would need an explicitly supported method. Part of the same **[Source Indexer](/projects/academic-hub/source_indexer/)** / **[RAG Analysis](/projects/academic-hub/rag_analysis/)** ecosystem the rest of **AI Research Assistant** builds on, feeding **[Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/)** directly.
