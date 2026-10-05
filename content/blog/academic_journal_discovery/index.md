---
title: "Automating Academic Literature Discovery: How to Pull Real Research Without Getting Blocked"
summary: "Why literature search isn't the bottleneck in AI research assistants — retrieving the actual full-text PDFs is. How I built a 5-tier legal download waterfall, used offline embeddings to keep API costs at zero, and designed an honest human-in-the-loop workflow when hitting publisher bot walls."
date: 2026-09-12
authors:
  - me
tags:
  - AI Research Assistant
  - Python
  - Hugging Face
  - LLM / RAG
  - Open Access
image:
  caption: 'Automated academic literature discovery pipeline from OpenAlex query and offline embedding scoring to 5-tier full-text waterfall and manual reconciliation'
  image_suggestion: "A software architecture and data-flow diagram for an automated academic literature discovery pipeline: showing faculty and topic queries feeding into OpenAlex, offline sentence-transformers scoring, a 5-tier full-text waterfall (Unpaywall -> Semantic Scholar -> CORE -> arXiv -> EZProxy), and a human-in-the-loop manual download worklist with automated text reconciliation."
---

Every graduate student and researcher knows the quiet dread of starting a literature review. You begin with an intriguing question or a faculty member's publication list, open forty browser tabs, hunt down DOIs, click through library proxy logins, and end up with a folder full of files named `main_revised_final(2).pdf` that you will inevitably have to search manually all over again.

<!--more-->

*Figure: Automated academic literature discovery pipeline from OpenAlex query and offline embedding scoring to 5-tier full-text waterfall and manual reconciliation.*

Most modern "AI research tools" promise to fix this, but in practice, they stop right where the hard part begins: they return a list of titles and abstracts. An abstract tells you what authors *claim* they found, but it never contains the actual econometric specifications, regression tables, proof derivations, or footnote caveats that real scholarship depends on. 

If you want an AI assistant or Retrieval-Augmented Generation (RAG) system that can genuinely synthesize literature alongside your coursework, it needs the **full text**. But building a pipeline to automatically retrieve academic papers immediately runs into the fragmented, defensive reality of scientific publishing: paywalls, conflicting APIs, and aggressive bot detection.

Here is how I designed and built the **[Journal Discovery Pipeline](/projects/ai-research-assistant/journal_discovery/)** — an automated, cost-conscious system that resolves faculty names and research topics into full-text PDFs, balances machine autonomy with human oversight, and respects the boundaries of real-world web infrastructure.

---

### 1. Beyond Keyword Search: Faculty Seeds and Citation Snowballs

A literature search rarely starts in a vacuum. Most research begins with a specific researcher whose work you admire or an empirical topic you are investigating. The pipeline provides two direct entry points:
```bash
# Discover papers by a specific faculty member
python -m discovery.journal_discovery --faculty "Daniel Björkegren"

# Or discover papers around an active research topic
python -m discovery.journal_discovery --topic "climate shock adaptation"
```

The pipeline queries [OpenAlex](https://openalex.org/), a massive open catalog of over 250 million scientific works. But standard search keywords only reveal a fraction of relevant work. The most natural way researchers uncover foundational papers is **citation snowballing**: taking a core paper and exploring everything that cites it forward in time.

The tool implements this as a two-stage, human-in-the-loop workflow:
1. `snowball propose`: Follows the OpenAlex citation graph for papers already in your local corpus, retrieves their citing works, and generates a structured candidate worklist (`snowball_candidates.md`).
2. `snowball confirm`: After you review and check off the papers you actually want, it downloads only those approved candidates.

By separating proposal from execution, the pipeline never pollutes your disk or burns bandwidth on papers pulled by citation graph volume alone.

---

### 2. Zero-Cost Pre-Filtering with Offline Embeddings

A naive approach to filtering candidates is to send every candidate title and abstract to a hosted LLM like Gemini or GPT-4. At academic scale, however, reading through hundreds of candidate papers burns paid API tokens rapidly — often on papers that turn out to be completely off-topic.

To eliminate this cost, the pipeline performs **offline semantic relevance scoring** using local, CPU-friendly `sentence-transformers` models from Hugging Face:
- You define a descriptive `--relevance-prompt` representing your research focus (for instance: *"Empirical microeconometric papers estimating household welfare impacts of weather shocks using satellite remote sensing"*).
- The pipeline computes dense vector embeddings for your prompt and for each candidate paper's abstract entirely on your local machine ($0 API cost).
- It calculates cosine similarity and filters candidates against a strict `--relevance-threshold` and `--max-results` ceiling before attempting any network requests for PDF files.

In a live trial seeded with an applied economist's publication record, this local filter evaluated his entire OpenAlex-indexed catalog in seconds, cleanly isolating the 19 genuinely relevant empirical papers without spending a cent on commercial APIs.

---

### 3. The 5-Tier Full-Text Access Waterfall

Once a paper is identified as high-value, the next challenge is getting the PDF. Academic literature is famously scattered across institutional repositories, preprint servers, and commercial publishers.

Rather than relying on brittle scrapers, the pipeline cascades through a five-tier waterfall, prioritizing free, open-access APIs before escalating to heavier methods:

$$\text{Unpaywall} \longrightarrow \text{Semantic Scholar} \longrightarrow \text{CORE.ac.uk} \longrightarrow \text{arXiv} \longrightarrow \text{Institutional EZProxy}$$

1. **Unpaywall**: The primary open-access oracle, querying millions of legal author-accepted manuscripts and publisher open-access copies.
2. **Semantic Scholar API**: Provides direct open-access PDF links across economics, computer science, and biomedicine.
3. **CORE.ac.uk**: Aggregates research outputs from university repositories worldwide.
4. **arXiv**: Direct lookup for preprints in mathematics, quantitative biology, and economics.
5. **Institutional EZProxy**: For subscription-gated publications, the pipeline authenticates through university proxy credentials (e.g. Columbia University EZProxy), pacing requests conservatively to protect institutional account standing.

---

### 4. When Automation Meets Anti-Bot Systems

Software architecture diagrams always look clean until they encounter production web defenses. 

During live testing through Columbia's EZProxy, attempting to download articles from major commercial publishers (such as Elsevier and Taylor & Francis) produced an immediate wall: `403 Forbidden`. 

The cause was not an expired library session or missing credentials. Inspecting the network exchange revealed **Cloudflare TLS fingerprinting**. Cloudflare evaluates the client's low-level TCP/TLS handshake and checks for browser-like JavaScript execution. Because a Python `requests` script lacks a browser's graphical execution engine, Cloudflare rejected the connection outright — even when accompanied by a completely fresh, authenticated university session cookie.

#### The Engineering Decision: Ethics vs. Anti-Bot Arms Races
In typical web-scraping tutorials, the recommended response to Cloudflare is to deploy stealth headless browsers (like undetected-playwright) or rotating proxy networks. 

For an academic software system, that is an anti-pattern. Attempting to bypass anti-bot challenges crosses an ethical and operational line: it shifts the software from *"retrieving literature our institution has already paid to license"* to *"actively attacking a commercial security perimeter."* Furthermore, automated fingerprint spoofing carries a real risk of getting university IP ranges or personal student credentials flagged and suspended.

#### The Pragmatic Fix: Automated Reconciliation
Instead of waging an arms race against Cloudflare, the pipeline accepts this boundary and handles it with an automated **human-in-the-loop worklist**:

1. Any paper that cannot be resolved automatically lands in a generated markdown file called `needs_manual_downloads.md`.
2. Each entry provides a direct clickable DOI link and names the exact destination folder created for that topic.
3. The researcher clicks the link, downloads the PDF in their normal browser (where their institutional login works seamlessly), and drops it into the folder.
4. A reconciliation pass (`reconcile_downloads.py`) runs during document conversion, scanning the converted text for the paper's DOI or title. When verified, the paper is automatically removed from the worklist.

In practice, this compromise works brilliantly. In a real 19-paper batch where bot walls blocked 16 automated downloads, manual downloading took less than three minutes, while the software handled all indexing, naming, folder routing, and metadata tracking.

---

### 5. Why This Matters: Feeding the AI Research Assistant

Extracting PDFs is not an end in itself; it is the foundational layer of the broader **[AI Research Assistant](/projects/ai-research-assistant-overview/)**.

Once verified, these papers pass into the **[Journal Article Transcription](/projects/ai-research-assistant/journal_article_transcription/)** pipeline, where multi-column layouts, mathematical notation, and tables are converted into clean, standardized Markdown tagged with paragraph-level citation identifiers (`¶N`). 

From there, the articles are indexed alongside textbook chapters and lecture notes in a unified vector database. When I ask a question in my RAG study tutor, it can draw upon both classroom theory and recent peer-reviewed literature — citing exact theorems from coursework and empirical findings from journal articles in the same synthesized breath.

Building this pipeline demonstrated an important truth about applied AI engineering: the hardest problems in agentic systems are rarely about prompting the model. They are about data engineering, respecting real-world system boundaries, managing API costs, and designing graceful handoffs between humans and machines.
