# Gemini / Antigravity image handoff

Prepared 2026-10-16. Editorial baseline: website commit `e85a808`.
**State: prepared for a manual handoff; no Antigravity agent has been started.**
The recommended visual direction below is provisional until the owner selects
it or approves pilot images. Neither a recommendation nor elapsed time counts
as approval for bulk generation.

## Ready-to-paste launch prompt

Open Antigravity with this dedicated website worktree as its project root:

`C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-website-images`

Paste the following:

> You own the image pilot on branch `gemini/website-images` in
> `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-website-images`.
> Verify the repository root, branch, and clean status before writing. Read
> `GEMINI.md`, `CLAUDE.md`, `docs/AGENT_ROUTING.md`, and
> `docs/editorial/gemini-image-generation-handoff.md` explicitly.
>
> Begin with the three pilot cards in that handoff. Read the linked page and
> its visible Insert Image block for each card. Use Antigravity's available
> image-generation capability under the owner's subscription. If it is not
> available in this session, report that limitation; do not substitute a paid
> API, use an unrelated credential, or claim that images were generated.
>
> Create one candidate per pilot, inspect each actual output, and save it in
> the specified candidate directory. Report any factual or visual defects
> honestly. Write the pilot review report, with paths to all three images.
> Stop for owner review before further generation or changes to page assets.
> The proposed style is navy, teal, and restrained violet, with simple
> editorial illustrations and very little text. Preserve the page-specific
> facts and distinctions. Scientific results must use original figures or
> standard plotting tools with verified source data, never imagined charts.
>
> Keep all writes in your assigned website worktree. Do not edit source
> repositories, other worktrees, layout/configuration, or new milestone blog
> drafts. Do not merge, push, deploy, or change publication status. Stage
> explicit task paths only. Begin now with the workspace checks and first
> pilot; preparing a plan alone does not complete this assignment.

The Gemini CLI installed on this computer is not evidence that this session
can dispatch an Antigravity agent. This is a manual file-and-prompt handoff;
the owner starts the Antigravity session. No new bridge or automation is needed.

## Ownership and scope

| Item | Assignment |
|---|---|
| Repository | Independent website Git repository, shared with `ai-sandbox/personal-website/AaronScherf.github.io`; not the outer monorepo |
| Gemini worktree / branch | `.worktrees/gemini-website-images` / `gemini/website-images` |
| Base | Committed readability work plus this handoff; see Git HEAD and the preparation record below |
| First write scope | `docs/editorial/image-candidates/` and `docs/editorial/gemini-image-generation-report.md` only |
| After explicit pilot approval and continuation | Exact existing page bundles in the 29-row queue below; image files, `image` metadata, and removal of the fulfilled Insert Image blocks only |
| Codex work | Separate readability worktree; new milestone blog bundles and their editorial evidence ledger |
| Read-only context | Existing pages and assets, their linked public status documents, and source code as needed |
| Out of scope | Whole-site redesign, layouts/CSS/configuration, unrelated assets, private coursework publication, new milestone drafts, and all merges/pushes/deployments |

Do not share the active Codex worktree with Gemini. Do not rebase this image
branch while another branch depends on its history; coordinate landing with
the integrator. Preserve any unfamiliar changes and stop writes on an
ownership mismatch. New blog image briefs created after this baseline are a
separate queue; do not silently expand the 29-image assignment.

## Are the existing descriptions sufficient?

They are good **content briefs**: all 29 specify a subject, explanatory
purpose, caption, alt text, and intended page-bundle asset. Many also say
what the picture must not imply. They are not complete production prompts
on their own: visual density, palette, typography, output dimensions,
factual review, and integration need consistent instructions.

Use the page's entire brief plus this style guide, not just its first
sentence. Work one page at a time, with the opening paragraphs as context.
Record the final generation prompt and its source page. If a brief conflicts
with verified behavior, flag the conflict rather than inventing a resolution.
The three pilots below make the key choices concrete before a large batch.

## Proposed visual direction

Keep the recognizable navy/teal/violet family; simplify the compositions.
This changes the image treatment, not the website's theme or layout.

- Default canvas: 1920 x 1080, 16:9, opaque background. If the tool cannot
  produce that exact size, generate the closest landscape format and export
  a deliberate 16:9 composition without stretching it. Keep the native
  original in the candidate directory.
- Suggested palette: navy `#14202D`, light ink `#F4F6F8`, teal `#35C9C8`,
  muted violet `#A58AE0`. Use light paper cards where they improve legibility.
  Scientific plots may use a light plotting area and their own clear legend.
- One explanatory idea per image, with one recognizable focal object or
  relationship. Favor clear document shapes, handwriting, source markers,
  a highlighted passage, or a visible review choice over abstract AI symbols.
- Usually two to four large labels. A brief may require more; reduce other
  detail first. Use one simple sans-serif typeface. Essential labels should
  remain readable when the full image is displayed about 390 pixels wide.
- Leave approximately 8% clear margin around essential content. The core
  idea should survive a 300-pixel-wide thumbnail even if secondary labels
  cannot be read. Check the actual collection card crop as well.
- Teal can connect sources to outputs; violet can distinguish a proposed or
  reviewed element. Also use words or shapes so meaning does not depend on
  color. Keep shadows and lighting subtle and consistent.
- Do not repeat the page title across the image, fill it with tool names,
  tiny equations, decorative terminal text, brand logos, neon plumbing, or
  a glowing brain. Avoid stock-like portraits and generic robots.
- Invented example content must be visibly illustrative. A source-reference
  icon means traceability, not proof of correctness. An AI check mark must
  not imply a person accepted the result.
- Do not fabricate screenshots, scientific measurements, successful runs,
  reviewer decisions, or public access to private notes. If long exact text
  renders badly, regenerate a simpler composition or add the approved words
  with a standard graphics tool; inspect the final pixels for spelling.

Inspect these existing assets for palette continuity, not as layouts to copy:

- `content/projects/academic-hub/source_indexer/featured.jpg`
- `content/projects/academic-hub/notes_transcription/featured.jpg`
- `content/blog/academic_hub/featured.jpg`

They currently use dense diagrams and small labels. Their color family can
remain while the page's new brief supplies a clearer subject.

## Three pilot cards

Use **one candidate per card**, then stop. These cover a missing first image,
a search explanation, and a before-and-after illustration. Existing assets
stay in place during the pilot.

### 1. Concept Graph: an arrow with a condition

- Read `content/projects/academic-hub/concept_graph/index.md`.
- Output: `docs/editorial/image-candidates/concept_graph/candidate-01.png`.
- Main composition: two spacious concept cards, left **Partial order**,
  right **Total order**, joined by one directional arrow. The arrow's label
  is **Every pair can be compared**. Add a small source marker and a restrained
  **Proposed** label belonging to the connection.
- This depicts the sample mathematical relationship, not the entire live
  graph and not its actual UI. No additional nodes, counts, formulas, or
  suggestion that the connection has been human verified.
- Thumbnail test: two concepts and their connecting condition remain the
  unmistakable subject. Article-size test: every word is correct and legible.
- Caption and alt text: take the complete proposals from the page's brief.

### 2. Source Indexer: find a passage, not just a file

- Read `content/projects/academic-hub/source_indexer/index.md`.
- Output: `docs/editorial/image-candidates/source_indexer/candidate-01.png`.
- Main composition: a small question cue leads through one course card,
  two staggered document cards, and a single enlarged passage with a generic
  page reference. Main labels: **Course**, **Document**, **Passage**.
- The brief's question is the intent to convey; it need not become a long
  headline. If used, spell **Where do my notes explain eigenvalues?** exactly.
  Use minimal invented passage text. Mark the whole example **Illustration**
  in the caption, not as a fourth large stage in the diagram.
- Do not depict a full search application or claim the illustration is an
  actual retrieved result. The passage reference should be visually attached
  to the passage rather than represented by a correctness badge.
- Caption: **Illustration: find the document, then the passage worth reading.**
  Alt: use the proposal in the page brief, adjusted to the actual final image.

### 3. Notes Transcription: preserve different kinds of information

- Read `content/projects/academic-hub/notes_transcription/index.md`.
- Output: `docs/editorial/image-candidates/notes_transcription/candidate-01.png`.
- Main composition: on the left, a generic slide with a handwritten margin
  question; on the right, two clean text regions labelled **Slide** and
  **Handwritten**, each connected to a source marker. The handwriting must
  remain visibly distinct from the slide's typed material.
- A small secondary notation inset contrasts **R²** with **R2**. It illustrates
  why superscripts matter. Do not bury the two source types under the inset.
- Use invented, brief material. Do not reproduce coursework or imply all
  handwritten equations are recovered perfectly. No cost-router diagram,
  tool-name inventory, or invented live interface.
- Caption and alt text: use the page brief, matching the actual final image.

## Later batches, after owner approval

1. Complete the other six missing featured images; Concept Graph is the
   seventh. The full missing-image set is Guided Solutions, Concept Graph,
   Summary Enhancement, Study Guide Pipeline, Project Steering, Corpus Health,
   and Socratic Tutor.
2. Complete replacement illustrations in batches of at most five, including
   the two replacement pilots once approved. The queue has 22 replacement
   briefs. Review existing assets before replacing them; any proposal to
   keep an existing asset needs an explicit recorded decision, not a silently
   skipped brief.
3. Handle the three scientific figures separately using the rules below.
   Nine additional pages already have images and no new brief; they are
   outside this generation queue.

### Scientific figures and semantic exceptions

- **Wheat Yield Prediction:** plot the exact environment-only holdout values
  from thesis Table 6: field random forest 0.829, field linear mixed model
  0.113; satellite random forest 0.746, satellite linear mixed model 0.243.
  Verify the linked original table before plotting; retain a reproducible
  plotting script and source reference. Use a shared R-squared axis. Do not
  invent scatter points, maps, or illustrative curves.
- **Math Thesis:** crop the actual power-comparison panels or reproduce
  verified simulation outputs. Preserve axes, labels, and conditions. If
  source figures/data cannot be accessed, leave this replacement blocked.
  Do not synthesize plausible-looking scientific results.
- **Visualization Sub-Agent:** capture or render the implemented gradient
  descent template for `f(x, y) = x² + 2y²`. Inspect its actual code and path.
  Do not invent controls such as a step-size slider.
- **Academic Hub overview:** shared converted sources and search support
  several separate uses. Guide generation and Concept Graph are parallel
  consumers, not successive automatic stages. Human review remains explicit.
- **Introducing Academic Hub:** this is the August introduction. Distinguish
  conversion already working then from sourced answers that were planned;
  do not illustrate October capabilities as already present in August.
- **Audio / commute post:** nine episodes include one 62-minute exception.
  Do not imply that every episode fits a short commute.
- **Obsidian / Excalidraw:** SVG export happens automatically on save;
  transcription makes the drawing searchable. App/plugin customization is
  editable source code, not a magical feature of every notes app.
- **Tutor, review, health and steering pages:** a suggestion, flagged issue,
  model verdict, or accepted priority is not a verified answer, completed
  repair, implemented task, or observed learning benefit.

## Integration after approval

Candidates stay outside `content/` until approved. Integrate an approved
image into the exact page bundle as `featured.jpg` or `featured.png`, with
correct file encoding. Do not leave two competing `*featured*` assets:
the current theme searches that wildcard before `image.filename`.
Git preserves the prior tracked version when replacing an approved asset.

Use this existing frontmatter map, preserving other keys:

```yaml
image:
  caption: "The approved caption, describing this image honestly."
  alt_text: "A concise description of what the final image shows."
  focal_point: Center
```

`alt_text` is the field used by the currently pinned HugoBlox article
template, verified in its cached `layouts/single.html`. `alt` alone is not
the correct field. Collection cards currently use a title-derived alt;
record that theme behavior rather than changing templates in this task.

Remove only the fulfilled `[[Insert Image: ...]]` block; do not alter the
article's prose, factual claims, dates, draft status, or source-link metadata.
Do not add a second inline copy of a hero image without a clear editorial
reason. Optimize final files sensibly (usually below 1 MB where legibility
allows); retain original candidates and exact prompts for review.

## Verification and completion report

| Capability | Scope, effects and cost | Output / repeat behavior | Evidence required |
|---|---|---|---|
| Read briefs and existing visuals | Assigned website; local reads only | Page and baseline recorded; no changes | Actual image inspection and page context |
| Generate pilot | Antigravity session's available image capability; subscription allowance is not measured here | Three candidate files; number reruns instead of overwriting | Open actual files; report misspellings and semantic errors |
| Owner review | Local candidate files and report | Pending / accepted / revise / declined recorded per candidate | Explicit owner decision; no automatic approval |
| Integrate accepted assets | Exact approved bundles only; no publication | One selected hero, caption and alt text; remove fulfilled brief | Diff, decoded file, and generated HTML |
| Build and render | Gemini worktree only; build writes ignored output | Local `public/` output; repeated builds do not expand scope | Production build plus article and collection checks |

For the pilot, write `docs/editorial/gemini-image-generation-report.md` with
one row per candidate: page, original brief path, exact prompt, tool/model
reported by the session (or unknown), actual dimensions, output path,
inspection findings, and **owner approval pending**. Link the full-size
images. Do not claim a style has been accepted merely because checks pass.

After integration is authorized, install the pinned dependencies in the
image worktree if absent (`corepack pnpm install --frozen-lockfile`) and run
`corepack pnpm run build`. Read `CLAUDE.md` for the Hugo requirement. Never
borrow another writer's generated output. Use a distinct local preview
port and inspect both the article and its collection card at desktop and
390-pixel mobile widths. Check file loading, crop, text legibility, caption,
article alt text, and whether the illustration communicates the intended
claim. A build passing does not establish those visual properties.

Final audit: every queue row is integrated, explicitly retained, or blocked;
each integrated page has one real featured asset; no fulfilled placeholders
remain; no dates/status/source links changed; no broken local image request;
no invented scientific data. Include unresolved items and owner decisions
in the report. Report quota stops without switching to a metered backend.
The integrator handles landing checks and approval under the repository's
workflow; do not merge or push from the image task.

## Preparation record

- Reviewed all 29 visible briefs and the 38-page coverage inventory.
- Inspected the existing Source Indexer, Notes Transcription, and introduction
  images directly. Confirmed consistent colors and excessive diagram density.
- Verified the pinned theme's image selection and article alt-text field.
- No image generation, candidate inspection, owner style approval, or live
  Antigravity session is claimed by this preparation record.
- The exact 29 page paths and content briefs follow in
  [the frozen queue](gemini-image-generation-queue.md). The source page in
  the image worktree remains the final check if a card and page disagree.
