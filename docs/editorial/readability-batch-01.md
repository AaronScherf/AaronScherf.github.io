# Readability revisions: batch 01

Prepared 2026-10-15. Status: revised text awaiting author review; publication
has not been requested. This batch covers entries 36–38 in the revised guide.
Its scope is three light blog edits, as requested, rather than the larger
project-page rewrites at the top of the queue.

## Versions and scope

- Website base: `e10f9b3`; branch: `codex/readability-batch-01`.
- Editorial guide: `website_page_readability_revisions_v2.md`, introduced
  in monorepo commit `cb91b36`.
- Supporting source checkout: monorepo `cb91b36`, read as reference material.
  No source pipelines or shared course/research data were run or modified.
- Existing URLs, original publication dates, tags, authors, and image assets
  are preserved. The posts have `lastmod: 2026-10-15`.
- Source examples come from documented workflow observations and recorded
  runs. There are no new claims of improved learning, measured sync speed,
  or an independently reproduced pipeline run.

## Pages prepared for review

| Guide entry | Page | Changes | Author review |
| --- | --- | --- | --- |
| 36 | [Why I Use Obsidian and Excalidraw for Academic Notes](../../content/blog/obsidian_excalidraw_notes/index.md) | Define the apps; show how a handwritten lecture note and a later version with slides connect; simplify sync language; date the later matching feature; retain export and maintenance tradeoffs | Pending |
| 37 | [Finding Academic Papers for a Research Library](../../content/blog/academic_journal_discovery/index.md) | Simplify catalog, scoring, and access language; preserve the early 3-of-19 result; add a dated disaster-recovery search example distinguishing relevant candidates from downloaded papers; clarify that conversion/search are separate steps | Pending |
| 38 | [Tidying Up Academic Hub's Plumbing](../../content/blog/academic_hub_infrastructure_cleanup/index.md) | Show why removing PDFs from the current folder alone did not remove their saved history; distinguish history cleanup from source-file relocation; explain tool grouping plainly; add a direct overview link | Pending |

## Evidence followed

The website project-page metadata and the monorepo's
`docs/trackers/subproject_registry.json` supplied code, status, and lifecycle
references. The registry is a navigation aid; its lifecycle labels were not
treated as proof that a feature had shipped. Status records and package
documentation were checked directly. The newer journal reliability spec and
plan are linked from its current status prose, beyond the older registry list.

- **Handwriting and slides:** the Source Indexer README's `related.py`
  description and the Obsidian Sync project page describe keeping both
  original notes and collapsing matched search results. The transcription
  README establishes the SVG/PNG export step and separate raw/expanded text.
  See the [indexer README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/core/indexer/README.md),
  [transcription README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/transcribe_notes/README.md),
  and [subset-note linking design](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/specs/indexer/2026-10-03-subset-note-linking-design.md).
- **Tablet maintenance and history cleanup:** the September 21 record
  documents heavy files retained in Git history and the cleanup. The
  September 26 record documents the switch to Fit and manual plugin-code
  copying. The relocation plan's recorded September 23 runs distinguish
  completed source-file moves from the earlier proposal. See the
  [September 21 record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-21-obsidian-git-sync-status.md),
  [September 26 record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-26-obsidian-git-sync-status.md),
  and [relocation plan and run notes](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/plans/convert_textbook/2026-09-21-source-asset-relocation.md).
- **Paper-search example:** the October 15 status records 15 accepted
  disaster-topic candidates, a direct relevance review, seven fetched PDFs,
  and eight manual-access entries. This is a later example, not a replacement
  for the earlier 3-of-19 trial. The package README explicitly keeps discovery
  separate from conversion/indexing. See the
  [current run record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/discover_journal_articles/2026-10-15-reliability-classification-and-validation-status.md)
  and [discovery README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/discovery/discover_journal_articles/README.md).
- **Software reorganization:** the September 29 status records the package
  grouping and full-suite pass after mechanical moves. The blog repeats
  that historical result; it is not a claim that the suite ran for this batch.
  See the [restructure status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-29-academic-rag-model-restructure-status.md),
  which links its design and implementation plan.

## Acceptance and validation

| Requirement | Evidence/status |
| --- | --- |
| Exactly the three selected posts revised | Prepared; inspect the three content diffs |
| Plain language and concrete, supported examples | Editorial pass completed; author's voice judgment pending |
| Historical context and original routes preserved | Original dates retained; later matching and search developments explicitly dated |
| Frontmatter and summaries reviewed | Required fields preserved; summaries edited; modification date added |
| No required visuals left unresolved | No images added or placeholders required for these light edits |
| Production build and search-index generation | Passed: `pnpm run build`, Hugo Extended 0.163.3, pnpm 10.14.0; Pagefind indexed 38 pages |
| Desktop and mobile rendering, links, and summaries | Chrome reviewed at 1440×1000 and 390×844; full-page screenshots inspected; no article overflow or runtime exceptions observed; local article links returned HTTP 200; all three updated summaries appeared in the blog listing and page metadata |
| Author approval and publication | Pending; website main remains at the batch base |

Existing feature diagrams remain dense and their small labels are hard to read
at mobile width. The prose explains the workflow independently. No replacement
visuals were generated in this light-edit batch; a separate visual pass can
address the diagrams after review.

Local render observations and screenshots are retained under the website
worktree's ignored `.agent-reports/readability-batch-01/` directory. These
artifacts are local review evidence, not files included in the public site.
The source pipelines and their historical test results were not rerun.

The guide entries remain incomplete until author review is satisfied. This
record provides the batch handoff without
prematurely checking off entries in the source repository's tracker.
