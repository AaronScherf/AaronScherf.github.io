# Readability revisions: batch 04

Prepared 2026-10-16. Five further project pages are prepared for review, starting
from website commit `8c3a32e` on `codex/readability-batch-01`. Work remains in
the same owned website worktree. Supporting monorepo reference: `7c2778c`.
Source repositories and documents are read only; no project pipelines run.

## Scope and acceptance

The next five project pages from the bottom of the revised guide are entries
24 through 20. The historical blog entry 28 remains deferred. This editing
request does not authorize publication or image generation.

| Requirement | Task and acceptance evidence | Status |
| --- | --- | --- |
| Revise five project pages | Project Steering, Corpus Health, Socratic Tutor, Wheat Yield Prediction, Normality Test thesis | Text prepared |
| Make the opening substantive | Explain a supported mechanism, decision, example, or result within the first two prose paragraphs | Completed; all five briefs follow paragraph two |
| Keep the prose accessible and interesting | Explain essential terms in context, preserve meaningful choices, and use distinct structures for software and research | Editorial pass complete; author review pending |
| Check evidence rather than inherit claims | Follow package/status/lifecycle references for software; check the linked theses and research repositories for the two research pages | Completed; decisions below |
| Preserve metadata and boundaries | Keep original dates, routes, assets, publication state, subproject links, and private source material | Passed; the wheat title and two image captions intentionally revised |
| Require image coverage | Retain existing featured images; add visible `Insert Image` briefs where absent, with purpose, composition, caption, alt text, and filename | Three missing-image briefs and two research-figure replacement briefs prepared |
| Validate the site | Production build; source/metadata/summary checks; desktop/mobile rendering and screenshot review | Passed; observations below |
| Preserve review stages | New wording and visual briefs await author review; assets and publication remain separate gates | Pending author review |

## Page map

| Guide rank | Page | Focus |
| --- | --- | --- |
| 24 | [Project Steering](../../content/projects/academic-hub/project_steering/index.md) | Move from a long task list to reviewed priorities; explain why changed task text invalidates earlier suggestions |
| 23 | [Corpus Health](../../content/projects/academic-hub/corpus_health/index.md) | Follow a missing search passage through discovery, review, narrowly scoped repair, and a final check |
| 22 | [Socratic Tutor](../../content/projects/academic-hub/socratic_tutor/index.md) | Explain checking replies against what the student has established, alongside the observed difficulty teaching unfamiliar material |
| 21 | [Wheat Yield Prediction](../../content/projects/wheat_yield_prediction/index.md) | State the evaluated prediction task, compare satellite and field information, and scope performance to the study |
| 20 | [Normality Test](../../content/projects/math_thesis/index.md) | Explain the bell-curve question, the pattern-based test idea, and its mixed simulation results |

## Sources and claim decisions

- **Project Steering:** the
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/tools/project_steering/README.md),
  [October 10 status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-10-project-steering-status.md),
  and registry-linked design establish the separate score/route review steps,
  stale-proposal handling, date gates, and on-demand execution. The trial-review
  example illustrates the date gate, not a newly approved or executed task.
  The 69-task result remains a dated parsing checkpoint, not a current count
  or evidence that its priorities are correct. No scan or owner-decision
  command was run for this editorial task.
- **Corpus Health:** the
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/tools/corpus_health/README.md),
  [first-adapter decision](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-09-corpus-health-apply-first-adapter-decision.md),
  design, and [trial handoff](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-09-corpus-health-implementation-retrospective.md)
  distinguish scan, review, and apply. Only exact-document passage repair is
  enabled, with current-record checks, an embedding cost, writer coordination,
  and an audit afterward. The transcript case is explicitly illustrative.
  A read-only check of local trial logs on October 16 found completed JSON/log
  pairs for October 12, 15, and 16, plus the October 9 manual launch; October
  10, 11, and 13 log files were empty and no October 14 pair was present.
  The latest report recorded a complete scan with zero scan errors. These
  observations do not establish why some logs are empty, that every day ran,
  or that all findings are valid. No scheduled task, scanner, or repair was
  executed or changed here. The public page gives the limited dated observation
  without disclosing local paths or source contents.
- **Socratic Tutor:** the
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/tutor/README.md),
  [status and live trials](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/tutor/2026-10-08-socratic-tutor-status.md),
  and v1.1 design distinguish locally checked session rules from the agent's
  dialogue. The two-session scope and teaching limitation appear in paragraph
  two. The exchange is labelled illustrative of the observed failure pattern,
  not a private transcript excerpt or an idealized successful tutor. Word-pattern
  misses, false matches, weak evidence, and rigid revisiting remain visible;
  permissive teaching is still a design direction.
- **Wheat thesis:** checked the public
  [thesis PDF](https://raw.githubusercontent.com/AaronScherf/wheat_yield_prediction_gee/master/reports/Aaron_M_Scherf_Final_Thesis.pdf)
  and [repository](https://github.com/AaronScherf/wheat_yield_prediction_gee).
  Printed pages 19, 21, and 33 describe processing and the 15% holdout. Table 6
  on printed page 34 (PDF page 42) distinguishes field-data random forest
  R² 0.829 from satellite-data random forest R² 0.746; the corresponding
  environment-only mixed-model values are 0.113 and 0.243. The page therefore
  compares matching data configurations rather than letting a headline 0.82
  imply satellite performance. Printed pages 40–41 support the computational
  and restricted-pedigree limits. The title is shortened, with the degree,
  advisor, year, original route, and thesis link preserved. The existing montage
  is captioned as an illustration and has a data-faithful replacement brief.
- **Normality thesis:** checked the public
  [PDF](https://raw.githubusercontent.com/AaronScherf/Novel-Omnibus-Normality-Test-and-Power-Comparison-with-the-Shapiro-Wilk-Test/main/MATH_Final_Thesis.pdf).
  Pages 1–3 explain the transformed-sample idea, page 13 the penalized model,
  and pages 14–18 the n = 20, 10,000-simulation comparisons and conclusion.
  The page retains mixed results and defines power without inheriting the
  original site's broad assertions about Shapiro–Wilk being only approximately
  omnibus or generally weak. The smoothing analogy explains the construction;
  it does not claim a generally better test. The existing montage is labelled
  illustrative, with a brief requesting original figures or plots made from
  actual outputs instead of generated scientific curves.

The browser fetcher could not retrieve the raw thesis PDFs, so the same public
URLs were downloaded into the ignored evidence directory for text extraction
and inspection of the relevant pages. The original PDF bytes and SHA-256
hashes are retained under `.agent-reports/readability-batch-04/sources/`.
No source PDFs, local operational logs, or private coursework are committed.

## Validation and remaining work

The final-text production build and Pagefind generation passed with Hugo
Extended 0.163.3 (119 pages; Pagefind indexed 38). Frontmatter, source targets,
excerpt markers, image-brief placement, and summaries passed source checks.
The original dates, routes, tags, publication state, assets, and subproject
metadata are preserved. All five pages have `lastmod: 2026-10-16`.

- Ten local Chrome browser checks passed at 390 × 844 and 1440 × 1000. Images
  loaded, no article overflow or runtime exceptions were observed, and local
  article links returned HTTP 200. Descriptions matched the source summaries
  in preview and production HTML. All five image briefs rendered in the body.
- All five summaries appeared on the appropriate collection page, without
  image-brief text in the excerpts. The two research tables fit on mobile.
- All five mobile screenshots and the two thesis desktop screenshots were
  inspected. Existing image labels remain small; the research replacements
  should use faithful source figures or plots made from actual results.
- Image coverage passed across all eighteen revised pages: eleven retained
  featured assets, seven briefs for first images, and two replacement briefs.
  New thumbnails cannot be checked until their assets exist.
- Evidence is under `.agent-reports/readability-batch-04/`, including source
  checks, coverage, trial observations, browser records, and screenshots.

The existing memory preview already held port 1329; a redundant launch failed
without changing it. Its owned PID and current page content were checked before
reuse. The setup report is retained under
`.agent-reports/bugs/20261016-readability-preview-port/`. This was not a
website defect, and no server or site configuration was changed.

No project pipelines, model evaluations, or new research simulations were run.
Author review, seven first-image assets across the cumulative batches, two
research-figure replacements, and publication remain pending. The cumulative
scope is eighteen revised pages; the other twenty guide entries remain for
later work, including the deferred historical blog entry.
