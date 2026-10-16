# Readability revisions: batch 02

Prepared 2026-10-15. Status: five further blog revisions prepared for author
review, alongside the requested Excalidraw correction. Publication approval
is separate from this editing request.

**Follow-up:** the author found the combined revisions too basic and asked
for slightly more technical substance across all eight posts. See the
[detail calibration](readability-detail-calibration.md) for the current pass;
the earlier results below apply to this batch's previous wording.

## Scope and progress

This continues the same owned website worktree and branch,
`codex/readability-batch-01`, while the first batch remains unpublished.
The correction is committed separately as `78e2294`, following the first
batch's `40f087f`. The five further edits start from `78e2294` and cover guide
entries 31–35. The guide and supporting monorepo source remain at `cb91b36`.

| Requirement | Task and acceptance evidence | Status |
| --- | --- | --- |
| Correct the author's description of Excalidraw | Explain automatic SVG export on save, the separate transcription operation, editable plugin source, and the tablet-control customization; check summary and conclusion for consistency | Text corrected; desktop/mobile rendering and updated summary checked; author confirmation pending |
| Revise the next five entries from the bottom | Entries 31–35 only; preserve the original dates, routes, required metadata, and publication state | Text prepared |
| Follow the shared voice and evidence rules | Short explanations and scoped examples; distinguish illustrations from recorded runs; retain historical context | Editorial pass complete; author review pending |
| Use linked project context | Follow project/status/lifecycle references to the supporting documentation and relevant implementation; record the sources below | Completed without running a source pipeline |
| Verify the website result | Production build, frontmatter/link checks, updated listing summaries, and desktop/mobile previews of all six changed posts | Passed; results below |
| Preserve review and publication boundaries | Keep first-batch review feedback distinct from approval of the corrected wording and the five new edits | Author review/publication pending |

This makes eight distinct posts prepared across the two batches. The author
reviewed the original three and requested changes to the Excalidraw post;
that correction and the five new revisions still need confirmation. No
project pages have been rewritten yet, and the source tracker is not checked
off prematurely. Existing diagrams are retained for a later visual pass.

## Five pages prepared

| Guide entry | Page | Editorial change |
| --- | --- | --- |
| 31 | [Managing this site with HugoBlox and Claude](../../content/blog/site_management/index.md) | Explain text files, review, and publication before naming the machinery; retain the documented homepage/project-page examples; simplify the summary and caption |
| 32 | [Converting Academic Resources to Markdown](../../content/blog/academic_resource_progress/index.md) | Explain what page references and figure descriptions let a reader check; identify the square-root error and add a dated update about its specific repair |
| 33 | [Making Textbook Conversion Easier to Run in Batches](../../content/blog/textbook_conversion_automation/index.md) | Illustrate one PDF reused across course folders; distinguish close-match confirmation from uncertain-match decisions; describe memory recovery as an operator/agent procedure rather than an autonomous orchestrator |
| 34 | [Indexing and Querying Academic Hub](../../content/blog/indexer_and_rag_progress/index.md) | Add an explicitly illustrative section/page reference and explain how it helps inspect an answer without guaranteeing correctness |
| 35 | [An AI Tutor That Gives Hints and Checks Your Reasoning](../../content/blog/pedagogical_rag_hints/index.md) | Replace the abstract preference-chain description with an explicitly illustrative hint; make the student's next action clear; simplify draft feedback and avoid repeated qualifications |

Each new post revision uses `lastmod: 2026-10-15` while retaining its original
date. Historical results remain scoped to their recorded run. The hint and
citation illustrations are not presented as transcripts from those runs.

## Sources and claim decisions

- **Excalidraw correction:** the author's direct feedback establishes that
  automatic export is part of saving, and that access to plugin source was a
  positive reason for choosing the app. The
  [notes-transcription status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/transcribe_notes/2026-08-24-notes-transcription-status.md)
  records automatic exports and the September 21 SVG change. The
  [September 26 sync status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-26-obsidian-git-sync-status.md)
  distinguishes plugin-code edits from interface-style changes and records
  the eraser/menu work and gesture-bar overlap fix. The local correction
  record retains the previous wording; batch 01's handoff has been updated.
- **Site management:** the website's `CLAUDE.md`, content files, and
  `.github/workflows/deploy.yml` establish the text-file/template setup and
  the automatic publishing workflow on `main`. The post's existing homepage
  and project-page examples are preserved as historical context. No new
  product-capability or performance comparison was added.
- **Conversion and the square-root repair:** the
  [textbook README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/convert_textbook/README.md)
  documents chapter/page markers and figure descriptions. The
  [post-processing status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/postprocess_notes/2026-08-27-notes-postprocessing-status.md)
  records the actual square-root repair and source-image comparison. The
  dated update closes that example without claiming all transcription errors
  are solved. The four/five-book counts are retained within their original
  validation scope, rather than presented as present-day totals.
- **Duplicate and recovery behavior:** the
  [duplicate-check implementation](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/core/indexer/duplicate_check.py)
  distinguishes exact reuse, high-confidence reuse pending confirmation, and
  less certain candidates needing a decision. Relevant planning context is
  [duplicate auto-resolution](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/plans/indexer/2026-09-20-duplicate-auto-resolution.md)
  and the [memory escalation plan](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/plans/convert_textbook/2026-09-20-oom-cost-escalation-ladder.md).
  The reused-PDF example illustrates supported behavior; it is not a new
  live-run claim. The escalation plan explicitly creates no orchestrator:
  the person or coding agent follows a documented sequence, with supporting
  counters and logs in code. The blog therefore separates that procedure
  from automated duplicate handling and from tests of supporting code.
  Test coverage and sustained batch reliability stay distinct.
- **References in answers:** the
  [RAG status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-08-30-rag-agent-status.md)
  records the spectral-theorem run and gives the citation-format example
  `§7.4 ... p. 264–266`. The blog uses a plain-language illustration of that
  format, not a fabricated quotation or attribution from the recorded answer.
- **Hints and checks:** the
  [tutor-diagnosis status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-09-27-tutor-diagnosis-status.md)
  and linked [design](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/specs/agent/rag/2026-09-27-tutor-diagnosis-design.md)
  establish non-spoiler hints, comparison with submitted reasoning, and a
  second solution without automatic adjudication. The new simple hint is
  labeled illustrative and is not a claimed new test or student outcome.

## Validation and remaining work

- Production build and Pagefind generation: passed using `pnpm run build`,
  Hugo Extended 0.163.3 and pnpm 10.14.0; Pagefind indexed 38 pages. The build
  was repeated after clarifying recovery as an operator/agent procedure.
- Six-post metadata, links, and listing summaries: passed. Original dates,
  authors, tags, publication status, and assets were preserved. The five new
  posts have updated summaries and modification dates; only site management's
  caption changed. All source references in the handoffs resolve locally.
- Desktop/mobile rendering, including the corrected Excalidraw post: Chrome
  inspected at 1440×1000 and 390×844, with twelve full-page screenshots. Images
  loaded, no article overflow or runtime exceptions were observed, all local
  article links returned HTTP 200, and metadata descriptions matched the
  updated summaries. The summaries also appeared in the blog listing.
- Author confirmation of these six revised texts: pending.
- Publication: pending explicit approval; website main is still at `e10f9b3`.

One initial parallel browser helper timed out awaiting image decoding.
Direct inspection found the image resources loaded; a bounded-wait recheck
completed the missing previews. This was not established as a website defect.
The initial output, helper, and investigation are retained under the ignored
`.agent-reports/bugs/20261015-preview-image-decode-timeout/` directory. Final
observations and screenshots are in `.agent-reports/readability-batch-02/`.

No new images or visual placeholders were introduced. The existing small
diagram labels are still a limitation at mobile width. Pipeline execution,
new performance measurements, and any changes to the underlying tools are
outside this editorial batch.
