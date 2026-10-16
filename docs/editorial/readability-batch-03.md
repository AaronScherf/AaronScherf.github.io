# Readability revisions: batch 03

Prepared 2026-10-16. Five project pages are prepared for review. The author accepted
the detail balance at `9da4b91` for now and requested substantive, interesting
material within the opening paragraph or two wherever possible. Further
recovery of detail can be considered in a later pass. Publication remains
separate from editorial approval.

## Scope and acceptance

Work continues in the owned website worktree on `codex/readability-batch-01`,
starting from `9da4b91`. The supporting monorepo is now `b43cb09`; unrelated
working changes there are left with their owners. Source material is read
only. Website configuration and source pipelines are outside this batch.

The five next project pages from the bottom of the revised guide are entries
30, 29, 27, 26, and 25. Entry 28 is a historical blog post and is deferred
because the author specifically requested project pages.

| Requirement | Work and acceptance evidence | Status |
| --- | --- | --- |
| Revise five further project pages | Guided Solutions, Concept Graph, AI Research Assistant overview, Summary Enhancement, Study Guide Pipeline | Text prepared |
| Make the opening substantive | A concrete mechanism, example, or meaningful decision in the first two prose paragraphs; review earlier eight openings too | All thirteen checked; two earlier openings adjusted |
| Preserve accessibility and interest | Explain terms in context; retain supported technical choices; avoid vague promises and unnecessary implementation inventory | Editorial pass complete; author review pending |
| Follow linked project context | Read page metadata and registry links to packages, status records, and their lifecycle references; resolve discrepancies against current documentation | Source review complete |
| Preserve site and source boundaries | Keep routes, dates, publication state, assets, and subproject metadata; label illustrations; do not publish private material | Metadata and source-reference checks passed |
| Verify the result | Production build, metadata/source-link checks, listing summaries, desktop/mobile render checks and screenshot inspection | Passed; evidence below |
| Keep review stages explicit | Earlier eight-post balance accepted for now; new pages and small opening adjustments need author review; publication not authorized | Pending author review |

## Page map

| Guide rank | Page | Opening substance and focus |
| --- | --- | --- |
| 30 | [Guided Solutions](../../content/projects/academic-hub/guided_solutions/index.md) | Keep student reasoning, agent derivations, and tutor-session proofs distinct; show a clearly illustrative layout and preserve the human-directed workflow |
| 29 | [Concept Graph](../../content/projects/academic-hub/concept_graph/index.md) | Explain connections with conditions through a sample-graph example; preserve the live graph, proposed/reviewed distinction, and unverified review-submission path |
| 27 | [AI Research Assistant](../../content/projects/ai-research-assistant-overview/index.md) | Use a labelled research-question illustration; explain abstract scoring, article access limits, conversion, and shared search across papers and notes |
| 26 | [Summary Enhancement](../../content/projects/academic-hub/summary_enhancement/index.md) | Explain the gap between remembering a result and working through it; describe expansion from the original source passages, paragraph provenance, and computed examples |
| 25 | [Study Guide Pipeline](../../content/projects/academic-hub/study_guide_pipeline/index.md) | Lead with topic-based source selection and reviewed edits; use the recorded textbook-section mismatch and actual review/apply run rather than invented guide quotations |

## Source decisions

The pages' `params.subproject` records and the monorepo's
[subproject registry](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/trackers/subproject_registry.json)
identify the package, status, membership, and lifecycle references. These
provided the source map for this pass; no index rebuild or source pipeline
was needed. All existing subproject metadata is preserved.

- **Guided Solutions:** the
  [run audit](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/problem_sets/2026-10-06-guided-solutions-proof-pipeline-status.md)
  records the human/agent separation and its October 8 update describes
  tutoring on two questions. The page's short layout is explicitly
  illustrative and contains no private coursework excerpt. The registry
  confirms this is an operational procedure without a standalone package,
  separate specification, implementation plan, or dedicated test suite.
- **Concept Graph:** the
  [current status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-15-concept-graph-status.md),
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/concept_graph/README.md),
  and linked design distinguish structural validation from content review.
  The example comes from the
  [sample graph's order connections](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/concept_graph/sample_data/data/edges/s01-binary-relations.yaml),
  identified as a sample rather than an inspected live-graph connection.
  The October 15 counts and test results remain dated, reported evidence;
  they were not rerun here. Unreviewed summaries, same-model critique, and
  the untested GitHub submission path remain visible. No graph data or live
  graph site was changed.
- **Research overview:** the discovery, journal-conversion, and essay-conversion
  READMEs linked by its three registry members establish the stages and their
  separate execution. Local abstract scoring and full-text access are kept
  distinct. The research question is labelled illustrative. The
  [current discovery status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/discover_journal_articles/2026-10-15-reliability-classification-and-validation-status.md)
  supplies current context; the
  [indexer README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/core/indexer/README.md)
  documents searching multiple collections. The overview makes no claim of
  a fully autonomous literature review or guaranteed article access.
- **Summary Enhancement:** the
  [current README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/summary_enhance/README.md),
  source loader/entry point, v2 design, and
  [status update](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/summary_enhance/2026-10-03-summary-enhancement-status.md)
  support using saved passages, paragraph/source records, separate output,
  and code-executed examples. The current interface takes precedence over
  older inline-tag and command examples. The statistical-test description
  illustrates the kind of expansion, without quoting a private guide or
  treating generated arithmetic as proof of sound explanation.
- **Study Guide Pipeline:** the
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/study_guide/README.md),
  original study-guide design/plan and guide-revision design, and
  [comparison record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-07-study-guide-comparison-status.md)
  support the source-plan, enhancement, and review/apply distinction. That
  record documents the textbook-section mismatch and the first review's
  27 accepted proposals and 18 text edits. Advisory notes and the superseded
  overlapping proposal are not counted as applied text fixes. The
  [microeconomics follow-up](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/2026-10-09-microecon-hw4-guide-status.md)
  establishes the need for an assignment-level check and hand repairs.
  Its decision to move toward subscription-agent drafting is a future design
  direction, not represented as an implemented replacement for the API tool.

## Earlier opening check

The eight previously revised posts were checked against the new opening
requirement. Six already introduce specific substance in the first two
prose paragraphs: abstract relevance scoring, measured sync-history cleanup,
editing/reviewing website source, conversion results with page references,
content-fingerprint reuse, and staged passage search.

Two received small adjustments without increasing their technical depth:
[Excalidraw](../../content/blog/obsidian_excalidraw_notes/index.md) now explains
automatic SVG creation and the separate transcription pipeline in paragraph
two; the [tutor post](../../content/blog/pedagogical_rag_hints/index.md) introduces
the second solver's independence there. Later repetition was shortened.
Automatic export, plugin-source customization, and the tablet fixes are
preserved. These two adjustments need review along with the five new pages.

## Validation and remaining work

- Production build passed using pnpm 10.14.0 and Hugo Extended 0.163.3:
  119 Hugo pages; Pagefind indexed 38 pages. The final build includes the
  clarification that accepted review proposals may be advisory notes.
- All seven changed pages passed metadata and source-reference checks against
  `9da4b91`. Dates, routes, authors, publication state, assets, and subproject
  mappings are preserved. The five new project revisions have summaries and
  `lastmod: 2026-10-16`; the two adjusted blog posts have that modification date
  too. Only the research overview's image caption was simplified.
- Fourteen browser checks passed in local Chrome at 390 × 844 and 1440 × 1000.
  Images loaded, no article overflow or runtime exceptions were observed, and
  local article links returned HTTP 200. Description metadata matched the
  revised summaries in both preview and production HTML.
- All five project summaries appeared on their relevant collection pages:
  the research overview at `/projects/`, and the four Academic Hub projects
  at `/projects/academic-hub/`. An initial helper incorrectly looked for all
  five in the top-level collection. Direct page inspection corrected that
  assumption; no website defect or layout change was established.
- All seven mobile screenshots were inspected, along with the Concept Graph
  and Study Guide desktop screenshots. The existing dense diagrams remain
  difficult to read on a small screen; new visuals are outside this batch.
- Local evidence is in `.agent-reports/readability-batch-03/`; the listing
  helper investigation is retained under
  `.agent-reports/bugs/20261016-project-listing-check/`.
- No project pipelines were executed and no new live-use or learning-outcome
  claims are made. Project test counts and run outcomes cited in the prose
  are source-checked historical records, not tests rerun by this edit.
- Author review of these five pages and two small opening adjustments remains
  pending. Publication requires separate approval. The earlier eight-post
  balance at `9da4b91` is accepted for now; future additional detail is deferred.

The cumulative scope is now thirteen revised pages: eight blog posts and
five project pages. The historical blog entry 28 and the remaining twenty-four
guide entries are untouched by this batch.
