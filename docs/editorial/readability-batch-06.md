# Readability revisions: final batch

Started 2026-10-16 from website commit `91502cb` on the owned
`codex/readability-batch-01` branch/worktree. Supporting monorepo: `7c2778c`.
Scope: the eight remaining project pages and two deferred blog posts in the
38-entry revised editorial guide. Source projects are read only; no project
pipelines, API calls, image generation, or publication are requested.

## Requirements and acceptance

| Requirement | Task and acceptance evidence | Status |
| --- | --- | --- |
| Finish the queue | Revise guide entries 1-8, 13, and 28; reconcile all 38 entries | Drafted; 38-entry inventory passed |
| Keep substance near the opening | Explain a concrete mechanism, example, choice, or result within two paragraphs | Completed; page map below |
| Readable and engaging prose | Explain necessary terms; retain supported detail and distinct stories | Pending author review |
| Check source context | Read linked package/status/planning records; resolve discrepancies against code where needed | Completed; decisions below |
| Historical blogs | Preserve original dates and perspective; separate later updates from historical results | Completed; two dated accounts |
| Preserve structure | Retain routes, publication state, tags, assets, and subproject mappings; review summaries and captions | Passed; audio title shortened, summaries/captions/lastmod revised |
| Visual coverage | Retain existing featured assets; add visible briefs below excerpts where useful | Ten retained assets and ten visible replacement briefs |
| Website verification | Production build, metadata/listing/link checks, desktop/mobile previews and screenshot inspection | Pending |
| Completeness handoff | Full queue inventory and remaining review/image/publication gates | Prepared; author assessment pending |

## Page and evidence map

| Guide rank | Page | Substance near the opening |
| --- | --- | --- |
| 01 | [Notes Transcription](../../content/projects/academic-hub/notes_transcription/index.md) | Separate slide text from handwriting; recover exponents using character size and position |
| 02 | [Marker PDF Conversion](../../content/projects/academic-hub/marker_conversion/index.md) | Preserve chapter boundaries and the distinction between printed and PDF page numbers |
| 03 | [Journal Discovery](../../content/projects/ai-research-assistant/journal_discovery/index.md) | Use a research angle to score abstracts; follow the dated 60/15/7/8 discovery result |
| 04 | [Visualization](../../content/projects/academic-hub/visualization/index.md) | Inspect the existing descent path on a contour plot; distinguish templates from generated code |
| 05 | [Source Indexer](../../content/projects/academic-hub/source_indexer/index.md) | Find a document and then a passage; preserve file identity across renames |
| 06 | [Resume Manager](../../content/projects/resume_manager/index.md) | Keep model output to bullets; replace slow model extraction with a parser |
| 07 | [Video Lecture Notes](../../content/projects/academic-hub/video_notes/index.md) | Combine recordings; explain how truncated input once lost two videos' content |
| 08 | [Problem Generation](../../content/projects/academic-hub/problem_generation/index.md) | Check the requested method separately from mathematical correctness |
| 13 | [Commute Podcasts](../../content/blog/audio_generator_podcasts/index.md) | Translate notation, then confront the historical three-hour recording |
| 28 | [Introducing Academic Hub](../../content/blog/academic_hub/index.md) | Preserve the original goal and working-versus-planned distinction from August 2026 |

## Sources and claim decisions

Package READMEs and the page metadata's status/lifecycle references supplied
the source map. Relevant source paths were clean at review time. No source
code, registry, tracker decisions, private course material, or personal
application files were changed. The examples use invented content or already
documented aggregate results.

- **Notes:** checked the transcription README, linked August status including
  its October addenda, and current PDF/router CLI defaults. The 13-page
  notation comparison and 43-page routing result are historical. Direct Word
  input is not advertised merely because relocation handles Word files.
  Current code supports subscription task cards and explicitly selected API
  operation; older status prose about the default is not treated as current.
  Automatic SVG export, separate raw/expanded notes, and expansion's
  interpretive risk remain explicit. Detailed anomaly scoring moves to the
  already revised post-processing page.
- **Textbooks:** checked the conversion README, chapter and image-description
  records, and later conversion/recovery status. Four-book page-label and
  five-book figure counts remain limited trials. The original malformed
  `96?98%` range is corrected to `96-98%`. Figure descriptions aid discovery
  but do not reproduce all plotted values; recovery tests and content checks
  remain separate evidence.
- **Discovery:** checked its README, September baseline, October 15 status,
  and the linked reliability/classification plan. `topic_proposals.py`
  explicitly reads stored OpenAlex Topics, not a paper's full argument.
  `tools/audit_metadata.py` establishes the older mechanical reconciliation
  operation. Those two authorities are separated. The October disaster
  trial's 60 retrieved, 15 accepted, 7 fetched, and 8 manual-access counts
  are scoped to that query. Discovery does not automatically run conversion.
- **Visualization:** the README and current gradient-descent template define
  the example's fixed descent path, contour surface, and available inspection;
  no parameter slider is invented. The September 6 status addendum supersedes
  the older unconfirmed combined-report claim. Gemini is the generation
  default; local generation is optional. Successful execution, a small
  example store, two backend successes, and mathematical correctness remain
  distinct. The code's execution environment is not called a security sandbox.
- **Indexer:** checked its README and core, passage, and cross-offering status
  records. The document/passage funnel, source-content identity, heading/page/
  paragraph locators, and handwriting-only containment comparison explain
  reader benefits. The 30-card/14-label checkpoint stays historical. Existing
  Corpus Health repair limits and review of uncertain links remain visible.
- **Resume:** checked the README, September bootstrap and tailoring records,
  page-fit plan context, and current `validate.py`, `tailor_resume.py`,
  `render.py`, and `apply_from_prompt.py`. Page fitting exists; the older
  statement that it is wholly future work is removed. A saved job-description
  route uses local tailoring, while the rough-opportunity route can call
  Gemini. Current qualitative checks are phrase/similarity/wording heuristics,
  not semantic guarantees. The 90-minute-to-1.5-second extraction comparison
  applies to the recorded resume. The hypothetical 12-project bullet is not
  presented as the author's experience. No applications were generated.
- **Video:** the README and September trial record support eight videos from
  a 105-video playlist and five indexed notes. The context-window correction
  improved coverage; reliable per-concept timestamps, surprising grouping,
  and full-playlist validation remain unfinished. The short example describes
  a format, not a private lecture excerpt. Indexing still has API calls.
- **Practice generation:** checked the README and September 6 backend,
  technique-check, and combined-report sections. The illustrative `1/n`
  exercise is newly composed and labelled. The nine successful trials across
  three topics do not erase earlier false acceptances or off-topic retrieval.
  The check is another model call, not an independent mathematical authority.
  The extracted problem bank remains separate from current passage examples.
- **Audio blog:** checked the audio README and September 9 timing record,
  consistent with batch 05's current project page. Keeps original October 1
  date and adds an October 16 update for the October 10 paragraph-splitting
  change. Separates 3.8-minute narration preparation from 19.4-minute synthesis
  and 23.2-minute total; nine files include the 62-minute exception. Corrects
  whole-source regeneration and removes unobserved listening/learning claims.
- **Introduction:** preserves August 2026 as an early announcement: textbook
  conversion working, sourced answering planned. Current project links are
  explicitly current. Simplifies workspace mechanics without carrying forward
  unsupported credential-isolation or never-overwrites guarantees.

## Verification and remaining gates

Before snapshots are preserved under `.agent-reports/readability-batch-06/`.
Author review of new prose and visual briefs, image creation, and publication
remain separate decisions. Passing website checks will not constitute new
validation of the projects described.


Final production build passed using `corepack pnpm run build` (pnpm 10.14.0,
Hugo Extended 0.163.3): 119 Hugo pages, with 38 pages indexed by Pagefind.
The bare `pnpm` command was unavailable on PATH; the existing Corepack
installation supplied the pinned version without a dependency change.

Metadata checks passed for all ten pages. Dates, URLs, authors, tags,
publication state, assets, links, and subproject mappings are preserved.
Summaries, captions, and `lastmod` changed; the audio blog's long subtitle
was removed from its title while preserving the URL. Each new brief is
visible after paragraph two, below the excerpt marker, with a suggested
caption, alt text, and featured-asset filename. Listing descriptions match
and contain no image briefs. Exact exponent and epsilon symbols match source,
production HTML, and browser text.

All twenty final browser records passed at 390-pixel mobile and 1440-pixel
desktop widths: no missing images, article overflow, or runtime exceptions;
local article links returned HTTP 200. All ten mobile screenshots and selected
desktop screenshots were inspected. The practice-generation page was checked
again after explaining the technical term in its second paragraph. Browser
records and before snapshots remain under `.agent-reports/readability-batch-06/`.

The [completeness review](readability-completeness-review.md) maps all 38 guide
entries to their edited files: 28 project pages and 10 blogs, with nine
unpublished template examples excluded. All 82 mapped code/README/status
paths across 23 mapped pages resolve locally, and local body-link targets on
all 38 pages exist in the production output. The optional website-sync
Git/lifecycle auditor could not start because the existing source virtual
environment lacks `jsonschema`; no dependencies were installed. The direct
checks above are narrower and do not certify that auditor's findings.

The [visual handoff](readability-visual-handoff.md) now covers 31 retained
featured assets, seven missing first images, and 22 proposed replacements.
All 29 image briefs must be resolved before publication. A generated brief
does not create a thumbnail, and retained posters still need visual review.
New author voice/depth review and the full-set assessment remain pending.
No source project accuracy tests, API workflows, teaching studies, image
creation, merge, push, or deployment occurred.
