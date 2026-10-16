# Readability calibration: accessible explanations with technical substance

Prepared 2026-10-15, following author feedback on website commit `29ad00f`.
Status: website validation passed; the author accepted the balance at
`9da4b91` for now. Publication remains pending.
Work continues on `codex/readability-batch-01` in the same owned website
worktree. The scope is the eight posts already revised, with no new pages.

## Updated editorial target

The author found the earlier revisions understandable but too basic. The
next pass should keep a nontechnical reader oriented while giving a technical
reader a concrete reason to follow the project link. This feedback supplements
the original readability guide for subsequent batches.

- Explain the use first, then name a specific mechanism, constraint, or
  tradeoff that makes the work interesting. Usually one or two such details
  are enough for a short post; use judgment rather than a quota.
- Preserve the difficult part of the story. A phrase such as "checks the
  output" is insufficient when the useful distinction is a separate solver
  that cannot see the first answer, or a comparison against a source image.
- Let documented decisions and results supply the excitement. Avoid vague
  promises, manufactured novelty, and rhetorical teasers without substance.
- Define an essential technical term in the sentence that introduces it.
  Deeper commands, schemas, thresholds, and development chronology still
  belong on linked project pages or in supporting documentation.
- Use a detail to explain why the project behaves as it does. More technical
  names alone do not make an explanation more useful.
- Put something substantive and interesting in the first paragraph or two
  wherever possible. The author requested this after accepting the initial
  balance; a later pass may recover additional useful detail. See
  [batch 03](readability-batch-03.md) for the opening checks and next five
  project pages.
- Every page needs at least one image suitable for its listing thumbnail.
  Preserve a suitable existing featured image; otherwise add a visible
  `[[Insert Image: Description]]` block during the prose pass for later Gemini
  generation. Each brief should explain the image's purpose and composition,
  include suggested caption and alt text, and identify the eventual
  `featured.jpg` or `featured.png` page-bundle asset. A text placeholder does
  not create a thumbnail. Replace it with the approved image before publishing.
  This author requirement supersedes the original guide's optional-visual
  rule. See the [visual handoff](readability-visual-handoff.md).
- Retain the author's corrections: SVGs are produced automatically on save;
  transcription makes them searchable; editable plugin code and interface
  styles are a practical advantage on the author's tablet.
- Keep run scope, historical context, illustrative examples, human decisions,
  and documented recovery procedures accurate. Technical interest must not
  turn a limited observation into a reliability or learning claim.

## Eight-post revision map

| Post | Specific substance to restore | Supporting context | Status |
| --- | --- | --- | --- |
| [Obsidian and Excalidraw](../../content/blog/obsidian_excalidraw_notes/index.md) | Why whole-note topical similarity confused separate lectures, and why comparing word sequences in the handwriting worked better | Indexer README, `related.py`, and subset-note linking records | Prepared |
| [Finding Academic Papers](../../content/blog/academic_journal_discovery/index.md) | Local embeddings for abstract relevance and a reviewed search following newer citing papers | Discovery README and `relevance.py` | Prepared |
| [Academic Hub's Plumbing](../../content/blog/academic_hub_infrastructure_cleanup/index.md) | The recorded repository-size reduction and content fingerprints that survive moves/renames while paths are reconciled | Sync status, indexer README, source-relocation plan | Prepared |
| [Managing this site](../../content/blog/site_management/index.md) | Hugo module boundaries and small local extensions without copying the whole theme | Website `go.mod`, `CLAUDE.md`, local hook | Prepared |
| [Converting Academic Resources](../../content/blog/academic_resource_progress/index.md) | Recovering mathematical notation using character size and vertical position before paid transcription | Notes-transcription status, August 26 structured-extraction section | Prepared |
| [Textbook Conversion in Batches](../../content/blog/textbook_conversion_automation/index.md) | Content fingerprints for exact duplicates and the reversible-reuse versus spent-GPU-time tradeoff | Duplicate-check implementation, duplicate auto-resolution plan | Prepared |
| [Indexing and Querying Academic Hub](../../content/blog/indexer_and_rag_progress/index.md) | Course/document/passage search and limiting how many passages one source can supply | Indexer README and RAG status | Prepared |
| [Tutor Hints and Reasoning Checks](../../content/blog/pedagogical_rag_hints/index.md) | The three-part draft rubric, a checker blind to the original solution/context, and a recorded missed-assumption example | Tutor-diagnosis status/design | Prepared |

## Evidence and review boundaries

The [batch-01 record](readability-batch-01.md) and
[batch-02 record](readability-batch-02.md) retain the source links and earlier
validation. Their author-review status now refers to superseded wording;
this pass needs a fresh review of all eight posts. The supporting monorepo
is `cb91b36`. Source pipelines, shared material, and website configuration
are read as context; this pass changes prose and editorial records only.

Additional direct references for the restored details:

- [Character geometry and mathematical notation](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/transcribe_notes/2026-08-24-notes-transcription-status.md).
- [Local abstract-relevance scoring](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/discovery/discover_journal_articles/relevance.py).
- [Handwriting-only word-sequence matching](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/core/indexer/related.py).
- [Source identities and staged retrieval](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/core/indexer/README.md).
- [Independent checking and rubric observations](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-09-27-tutor-diagnosis-status.md).

The previous eight source texts were preserved before editing under the
ignored `.agent-reports/bugs/20261015-editorial-detail-calibration/before/`
directory. The associated report records an editorial mismatch, not a
diagnosed software failure. The author is the reviewer for voice and depth;
no reviewer has been contacted through an external service.

## Acceptance and validation

- All eight posts now carry a concrete, source-supported explanation of an
  interesting choice or difficulty while retaining their accessible opening.
  Each gained 28–58 words; the longest is 431 words. These counts describe the
  scale of the edit, not author approval of its tone.
- Original dates, routes, authors, publication state, and approved Excalidraw
  facts are preserved. Summaries were reviewed for appropriate specificity.
- Production build passed with Hugo Extended 0.163.3; Pagefind indexed 38 pages.
- Browser checks passed for all eight posts at 1440 × 1000 and 390 × 844:
  images loaded, no horizontal overflow or runtime errors, and local article
  links returned HTTP 200. Listing summaries and description metadata matched
  the revised text.
- Mobile screenshots and selected desktop screenshots were inspected. Existing
  diagrams with small labels remain a separate visual improvement opportunity.
- Local evidence is under `.agent-reports/readability-detail-calibration/`.
  Source pipelines were not rerun; historical results were checked against
  their supporting records.
- Author judgment of the balance at `9da4b91`: accepted for now; a future
  detail pass remains an option. Batch 03's small opening adjustments need
  their own review.
- Publication: pending explicit approval; no website-main changes authorized.
