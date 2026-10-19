# Historical milestone drafts: first selection

> **Publication review, October 19:** This document records the original drafting baseline. The resume-parser and study-guide posts now have reviewed featured images and are prepared for publication on `codex/milestone-blog-publication-review`. The practice-problem, lecture-question, and concept-map posts remain drafts because their first image candidates need factual corrections. See [the image review](milestone-blog-image-report.md) and [correction handoff](milestone-blog-image-corrections.md). Nothing is live until the branch is merged and deployed.

Prepared 2026-10-16. Source repository inspected at `d0fced1`; website
editorial baseline `e85a808`. All five new posts are **unpublished drafts**.
This is a reconstruction from recorded development, not a claim that these
posts existed or were published on their displayed milestone dates.

## Purpose and boundaries

Add useful dated stories between the ten existing blog posts, without
rewriting the project pages as a second blog inventory. Follow the accepted
readability/detail balance: a concrete hook in the opening, one revealing
technical decision explained through its use, and evidence with its scope.
Each post has a visible retrospective note and links to a fixed historical
revision. The body describes that checkpoint; links to current project
pages give readers a route to subsequent developments.

The existing blog already covers the project introduction, resource and
textbook conversion, initial indexing and answers, journal discovery,
Excalidraw, hints, audio, website work, and infrastructure cleanup. These
five add practice generation, a practical application outside coursework,
saved answers to handwritten questions, reviewed guides, and the course map.
The unrelated untracked draft in the main website checkout was left intact.

No source pipeline, paid API, image generator, indexer, or live coursework
run was invoked. Git and source documents were read locally. No private
resume, notes, assignments, generated guides, or task cards were copied
into these public-repository drafts. Examples use published status facts
or clearly identified sample data.

## Drafts and proposed milestone dates

| Date | Draft | Distinct story and opening substance |
|---|---|---|
| 2026-09-06 | [A Practice Problem Can Have the Right Answer and Still Miss the Point](../../content/blog/practice_problem_checks/index.md) | A flawed proof passed its own check; separate method and correctness verdicts exposed a different failure. Includes the scoped nine-trial cloud comparison. |
| 2026-09-09 | [The Resume Step That Became Faster When I Removed the AI](../../content/blog/resume_parser_milestone/index.md) | One import fell from over 90 minutes to about 1.5 seconds after a parser replaced model-based field extraction. |
| 2026-10-04 | [Giving the Questions in My Lecture Notes Somewhere to Go](../../content/blog/questions_in_lecture_notes/index.md) | Seven saved answers, four with course passages and three without; explains self-source exclusion and why answers live beside regenerated notes. |
| 2026-10-09 | [A Long Study Guide Still Needs to Answer the Right Questions](../../content/blog/reviewable_study_guides/index.md) | An eleven-topic guide still missed assignment coverage; source selection and individually reviewed edits made the defects easier to investigate. |
| 2026-10-15 | [A Course Map Where the Arrows Have to Explain Themselves](../../content/blog/concept_map_conditions/index.md) | Conditions and source references make connections inspectable; the real course graph reached 104 concepts and 159 connections in eight sections. |

The question-resolver date deliberately uses **October 4**, when the live-run
status was committed. Its filename says October 3, and implementation began
that evening; fixes and the committed outcome record extend into October 4.
We do not assign the complete recorded result to the earlier date.

## Evidence ledger

Repository-relative paths below belong to the outer monorepo. Inspect them
with `git show <SHA>:<path>`; current file contents are not substitutes for
these fixed revisions. The historical paths account for directory moves.

### Practice problems — September 6

- Status revision: `5c78c2e3d47939869c2f077e1c479d7500dad832`, committed
  2026-09-06 15:41 Eastern, at
  `ai-sandbox/academic-rag-model/docs/2026-09-05-problem-generation-status.md`.
- Read the real generation runs, self-verification limitations, September 6
  constraint trials, split verdict implementation, and feasibility spike.
- Recorded observations: flawed local proof accepted by the model; requested
  method ignored despite prompt emphasis; two constrained local trials with
  no accepted output; nine cloud trials across three topics, all passing
  model checks and hand inspection; weak use of contradiction and repeated
  probability problems still noted.
- The cloud comparison was explicitly a standalone script at this revision.
  The post does not backdate its later integration or treat nine observations
  as a general success rate. The comparison uses unequal samples/topic sets.
- Code and fixture checks establish the verdict parser/control flow; the
  documented actual trials establish only those outputs. No learning gains
  are inferred.

### Resume parser — September 9

- Implementation: `467810757813902dea015abf4d1114b27a0b0d17`, committed
  2026-09-09 21:50 Eastern, changes
  `ai-sandbox/academic-rag-model/resume_manager/normalize.py`.
- Same-day status: `fb184576380d2e980751c08f0c26c3a1035f9860`, committed
  2026-09-09 22:45 Eastern, at
  `ai-sandbox/academic-rag-model/docs/status/2026-09-09-resume-manager-status.md`.
- Recorded observations: free-form fields confused role locations with dates;
  a structured model-based import took over 90 minutes and retained content
  defects; deterministic parsing reduced initial import to about 1.5 seconds
  on the recorded resume. Per-application language tailoring remained a
  separate model step.
- Runtime is initial import only, not a complete application. This is not
  evidence that arbitrary PDF layouts parse reliably. Fixed-field copying
  does not guarantee that rewritten bullets preserve every implied claim.
- Excludes later guidance preferences, interactive clarification, cloud
  opportunity extraction, and September 27 multi-source merge findings.

### Handwritten questions — October 4

- First implementation includes `d74f8598be38ca4be6bb6d68ee41507b50346ce9`,
  committed 2026-10-03 22:02 Eastern.
- Outcome record: `662696bf96f0519a2140e00c328d6b0049acf7e6`, committed
  2026-10-04 13:54 Eastern, at
  `ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-10-03-question-resolver-status.md`.
- Recorded actual run: four notes, seven questions, four grounded and three
  ungrounded answers; one source-backed explanation spot-checked; file-level
  search found a companion answer file. Passage chunking remained pending.
- Implemented behavior: exclude the note's own files, store answers in a
  companion file, keep markers linked through regeneration, and label
  general-knowledge answers. Grounding is a retrieval label, not proof that
  the source supports every sentence or that the answer is correct.
- Does not backdate the October 16 consolidated orchestration or the later
  subscription-agent resolver. Saving a drawing is not an automatic resolver
  trigger in this post.

### Study guides — October 9

- Status and README revision: `bbcf843bac181794e37c47772fe82ff57ac97b54`,
  committed 2026-10-09 19:33 Eastern.
- Paths:
  `ai-sandbox/academic-rag-model/docs/status/agent/2026-10-09-microecon-hw4-guide-status.md`
  and `ai-sandbox/academic-rag-model/agent/study_guide/README.md`.
- Actual run: eleven topics, draft plus one enhanced section, accepted
  revisions, and hand repairs. The assignment check found missing coverage
  and mathematical defects beyond those caught by the model audit.
- Implemented workflow: source plan and review; separate proposed revisions;
  deterministic application into a revised copy; untouched-block checks and
  rejection of a review against changed input. These checks constrain edits;
  they do not certify mathematical correctness.
- Subject-neutral prompting, per-course relevance tuning, and a subscription
  agent as the default were follow-up work at this checkpoint, not completed
  capabilities. The post preserves that distinction.

### Concept graph — October 15

- Status revision: `730c7c24cea346664a3028312996dd2a2b6efa60`, committed
  2026-10-15 01:27 Eastern, at
  `ai-sandbox/academic-rag-model/docs/status/agent/concept_graph/2026-10-15-concept-graph-status.md`.
- Sample relationship checked in the same revision at
  `ai-sandbox/academic-rag-model/agent/concept_graph/sample_data/data/edges/s01-binary-relations.yaml`:
  total order / partial order with the completeness condition. The prose
  illustrates adding comparability; it does not claim an exact screenshot
  or copy the stored edge's orientation.
- Recorded live graph scale: 104 concepts, 159 connections, eight sections.
  Implemented viewer and review controls are distinct from the unexercised
  GitHub proposal-submission path. Model-drafted summaries remain unreviewed;
  model self-critique may be lenient.
- Passing Python/viewer tests are not presented as evidence of mathematical
  correctness, completed content review, or learning benefits. The linked
  live page is mutable; the post labels it accordingly.

## Requirements and review gates

| Requirement | Implementation | Acceptance evidence / remaining gate |
|---|---|---|
| Use Git and historical status versions | Five dated snapshots, path moves checked, implementation corroboration where useful | Fixed SHA/path ledger above; no new live runs claimed |
| Accessible, substantive openings | Concrete failure, change, or claim within the first two paragraphs | Editorial pass complete; author's voice/content review pending |
| Tell development stories rather than duplicate project summaries | Each post centers on one decision and links current project details | Review against ten existing posts; owner selection pending |
| Explain scaffolding | Notes to search to saved answers; selected passages to guides; same sources to graph | Contextual links in the relevant posts; no invented automatic graph/guide dependency |
| Backdated events with honest authorship timing | Historical `date`, actual `lastmod: 2026-10-16`, visible retrospective note | All five `draft: true`; publication approval still required |
| Featured image for every published page | Five substantive visible Insert Image briefs below paragraph two | No new assets yet; image generation/integration required before publication |
| Isolated Gemini image work | Separate image worktree based on `5096eb4`, before new posts | Existing 29-page image queue excludes these five new drafts |
| Preserve current site | No existing page or configuration changes in this drafting pass | Production build passes; draft routes absent from output, listing, feeds, and sitemap |
| Review rendered drafts | Local build with drafts and desktop/mobile inspection | Ten browser records pass; representative screenshots inspected; author review pending |

## Image follow-up

The separate Gemini worktree contains the existing 29-image assignment.
These five new briefs are not in that worktree or queue. After its pilot is
accepted, the owner can explicitly add the five blog images by giving Gemini
the committed new bundles or a new task base. Do not ask Gemini to read the
live Codex worktree or change its scope silently. All five posts remain
drafts while images and content review are pending.

## Validation record

- `corepack pnpm run build`: passed, Hugo Extended 0.163.3; 119 pages,
  Pagefind still indexes 38 substantive pages.
- Production exclusion: all five new article routes are absent from `public/`;
  blog listing, main/blog feeds, and sitemap contain none of their URLs.
- Separate `hugo --buildDrafts --minify --destination
  .agent-reports/milestone-blog-drafts/site`: passed. This review build
  intentionally includes all drafts, including the site's existing template
  examples; it is not a publication build.
- All five new frontmatter maps parse; `draft: true`, milestone dates,
  `lastmod`, titles and summaries are present. Each has one visible image
  brief after paragraph two and below the excerpt marker. All five rendered
  articles include their retrospective note. Body length, excluding image
  instructions, is 421–448 words including historical notes.
- Historical links were checked against local Git objects: every pinned
  commit and file exists at the stated revision. This checks repository
  history, not whether an unpublished source commit is reachable on GitHub;
  remote availability must be checked before publication.
- Ten browser checks: all five drafts at 390 x 844 and 1440 x 1000. Local
  article links return HTTP 200; no failed image requests, content overflow,
  or JavaScript runtime exceptions were found. Inspected representative
  full-page screenshots of the practice post on mobile and graph post on
  desktop. This is a rendering check, not reader testing.
- No featured assets exist for these five new posts yet. Passing image-request
  checks means there are no broken requests; it does not satisfy their
  featured-image requirement. The visible briefs deliberately remain.
- Local source/metadata, production-exclusion, draft-HTML, and browser evidence
  is saved under `.agent-reports/milestone-blog-drafts/` (ignored).
- The writer's meaning and voice still need author review. Dates are proposed
  milestone dates; none of these drafts has been merged, pushed, or published.
