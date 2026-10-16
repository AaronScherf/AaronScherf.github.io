# Holistic portfolio review

Started 2026-10-16 from website `5d10fd4`, on the owned
`codex/readability-batch-01` branch/worktree. All 38 substantive page bodies
were read together, including their summaries. The existing project collection
introductions were also inspected. Source checkout at review: `d0fced1`;
source files and private course/research material are read only.

## Requirements and acceptance

| Requirement | Review and action | Acceptance evidence | Status |
| --- | --- | --- | --- |
| Consistent claims | Compare shared counts, backends, histories, source references, and integration limits | Claim matrix and source decisions below | Completed within the recorded evidence scope |
| Engaging substance | Check every opening for a concrete use, mechanism, example, or result | 38-page review inventory | Completed editorial review; author judgment remains |
| Accessible language | Check unexplained terminology, repeated qualifications, and editorial history in public copy | Focused wording changes; retain distinct voices and examples | Completed |
| Collective usefulness | Explain what a student or researcher can accomplish across the tools | Overview and collection introductions | Completed |
| Explain scaffolding | Trace conversion and search to answers, summaries, guides, and concept maps | Verified reader paths and contextual links in both directions | Completed |
| Preserve boundaries | Keep hypothetical examples, historical posts, review decisions, publication state, and unimplemented integrations distinct | Metadata, brief, and source checks | Passed |
| Verify changes | Build, local link/metadata checks, desktop/mobile previews | Saved records and screenshot inspection | Passed; 46 final browser records |

This is an editorial review of established behavior. It does not authorize
new pipeline runs, new integrations, image generation, publication, or changes
to site layout and navigation. Local prose fixes stay within existing pages
and collection text.

## Initial findings

1. The conversion and indexer pages explain their mechanisms, but provide too
   few routes to the study outputs they enable. Conversely, guides and concept
   maps mention retrieved material without explaining the common foundation.
2. Several different outputs are called summaries: catalog descriptions,
   saved study answers/recaps, expanded guides, and concept-graph section
   overviews. Their roles need distinguishing without exposing schemas.
3. The existing collection introductions still use the older technical and
   promotional vocabulary. They are entry points to the rewritten pages.
4. A few pages discuss an older website description or an obsolete validation
   note. That editorial history obscures the current capability.
5. Shared substantive claims are mostly consistent. Important boundaries
   remain: the extracted question bank does not feed generation yet; audio
   generation is not an automatic summary-to-podcast workflow; and the
   Socratic Tutor is separate from RAG's hint and draft-feedback tools.

## Assessment

The pages collectively cover the interesting parts of the work: recovering
mathematical structure, choosing when to use a model, retrieving precise
passages, preserving references across generated outputs, representing
conditions on conceptual relationships, separating student and agent
contributions, and making review decisions inspectable. The thesis and resume
pages have distinct purposes and do not need to be folded into Academic Hub.

The main weakness was connective explanation, rather than missing component
pages. A reader arriving through a conversion page could understand how it
worked without learning why it mattered to a guide or map. The focused pass
adds those handoffs and removes a few pieces of editorial bookkeeping from
public prose. Nineteen substantive pages and three existing collection
introductions changed; the other nineteen substantive pages were reviewed and
retained. No templates, menus, layouts, or new product interfaces were added.

### Useful paths through the project

| Reader's task | Connected tools and what each contributes |
| --- | --- |
| Revisit a question in handwritten notes | Notes Transcription preserves handwriting and slide distinctions; Source Indexer finds the relevant passages; RAG Analysis drafts an answer with source references |
| Turn a short answer into something to study | RAG saves an answer or recap with passage references; Summary Enhancement reopens those exact passages and develops explanations and worked examples |
| Prepare a guide for a topic list | Converted notes and textbooks supply indexed passages; Study Guide Pipeline selects sources, drafts, optionally enhances, and proposes edits for review |
| Understand why a result follows | Concept Graph uses the indexed material to draft ideas and condition-bearing connections; a reviewer inspects the claims and evidence |
| Find literature beside an old research idea | Discovery obtains available papers; article and Word-note conversion prepare text; the shared index searches both collections and supplies passages for RAG answers |
| Practice and compare reasoning | Problem Generation uses indexed course examples; Tutor Diagnosis gives one-off feedback; Socratic Tutor manages a separate conversation; Guided Solutions preserves different contributors' work |
| Listen to notes | Audio Generator reads note/textbook text directly; the indexer is not a prerequisite, and an automatic weekly-summary-to-audio integration is not established |
| Keep the material usable | Sync keeps working notes available; Corpus Health checks source/output/search gaps; Project Steering supports decisions about development priorities |

These are available tool relationships and supported ways to combine them,
not a new live end-to-end validation or a promise that a single command runs
every stage. In particular, a concept map and a study guide are parallel
outputs of the shared material: neither automatically produces the other.

### Terms that needed separating

| Term in context | Meaning |
| --- | --- |
| Catalog description | A short index record used to find a document; not a study guide |
| Transcript and expanded lecture note | Source conversion outputs, with expansion adding interpretation that needs checking |
| Saved answer or session recap | A study note written by RAG; stored passage references allow later expansion |
| Enhanced summary | A fuller guide based on those recorded passages, with source-based explanation and generated examples distinguished in its records |
| Study guide | A topic-led drafting and revision workflow, which can use the same enhancement step |
| Concept-map section overview | A short overview within the graph viewer; separate from Summary Enhancement |

## Claim consistency and source decisions

| Shared claim | Source checked and decision |
| --- | --- |
| Conversion enables passage-based tools | Notes/textbook READMEs and `core/indexer/README.md` establish registration and passage search; new links explain the downstream use without promising that every raw file is already indexed |
| Saved summaries preserve usable source identities | RAG README's saving section and `agent/rag/report_builder.py` retain file/passage references; `agent/summary_enhance/source_loader.py` loads them directly instead of running a fresh similarity search |
| Guide and map share infrastructure | Study Guide README and Concept Graph README/`sources.py` establish retrieval from the indexed collection through their separate drafting stages |
| Concept connections need conditions | Concept Graph README and viewer/status records support condition-bearing arrows and proposed-versus-reviewed content; graph counts remain the dated October 15 checkpoint |
| Backend and cost descriptions | Notes/article subscription handoffs remain distinct from metered indexing; visualization and problem generation default to Gemini; video synthesis is local with API indexing; resume's saved-description route is local while the rough-opportunity route can call Gemini |
| Episode behavior | Blog and audio project agree on whole-source regeneration, the historical nine files/62-minute exception, and the later paragraph-splitting change |
| Source and question-bank coverage | The 13-page notation check, four-book page-reference check, five-book image pass, and 196 extracted-question run retain their original scopes; counts are not treated as accuracy scores |
| Discovery and classification | Both discovery descriptions distinguish relevant candidates from obtained PDFs; stored OpenAlex Topics proposals remain separate from the older mechanical metadata audit |
| Study tools are different tools | RAG answers/hints, tracked Socratic conversation, authored solution documents, topic-led guides, and maps have distinct uses; cross-links explain the choices without inventing integrations |
| Maintenance is not broad automatic repair | Corpus Health retains its exact-card repair boundary; priority review does not start implementation; the extracted bank is still separate from generation |
| Historical blogs | August's introduction remains historical; later discovery, notation, and audio changes stay dated; the blog's regeneration paragraph now states behavior directly instead of discussing a previous website claim |
| Independent research | The normality and wheat-yield pages retain their own methods, held-out/simulation conditions, limitations, and source links; neither is presented as an output of Academic Hub |

The source checkout advanced since batch 06. Its current consolidated notes
orchestrator coordinates transcription, question resolution, and passage
indexing; its implementation and October 16 spec/plan were inspected. The
spec header still calls it unimplemented, while current code contains the
coordinator. This review uses code to establish the relationship, and makes
no new claim of successful live operation. Subscription collect/submit still
requires handoffs; pending work is not a completed corpus refresh. Source
documentation was not edited in this website task.

## Language and opening review

Every opening was read for an intelligible purpose and a specific reason to
keep reading. The technical detail is carried by choices and examples rather
than a list of implementation names. The following inventory records the
editorial judgment, not a measured comprehension score.

| Rank | Page | Substance retained in the opening or immediate explanation | Action |
| --- | --- | --- | --- |
| 01 | Notes Transcription | Handwriting/slide attribution and local exponent recovery | Add search-to-guide/map path |
| 02 | Marker PDF Conversion | Chapter boundaries and printed versus PDF pages | Add indexed downstream uses |
| 03 | Journal Discovery | Research-angle scoring and dated download funnel | Retain |
| 04 | Visualization | Inspecting an actual descent path; templates versus generated code | Remove obsolete validation-history aside; link practice report |
| 05 | Source Indexer | Document-to-passage search and content-based identity | Separate catalog descriptions from study notes; link principal consumers |
| 06 | Resume Manager | Facts copied by code; parser's measured bootstrap improvement | Make illustrative tailoring emphasis clearer; remove website-edit history |
| 07 | Video Lecture Notes | Combining recordings and the lost-context finding | Retain |
| 08 | Problem Generation | Requested method checked separately from correctness | Link source retrieval |
| 09 | Tutor Diagnosis | Correctness, justified steps, and course fit | Retain |
| 10 | RAG Analysis | Source references and limits on one file's contribution | Explain saved-note expansion path |
| 11 | Obsidian Git Sync | Lightweight cross-device notes and current Fit mechanism | Retain author corrections and manual plugin transfer limit |
| 12 | Research Notes Conversion | Direct Word parsing and paragraph locators | Explain indexing as catalog/search work; link indexer |
| 13 | Commute Podcasts | Notation-to-speech and the three-hour recording | State regeneration behavior directly |
| 14 | Notes Post-Processing | Square-root corruption and context on both sides | Retain |
| 15 | Problem Corpus | Student attempts remain distinct from answer keys | Retain separate-bank boundary |
| 16 | Audio Generator | Formula translation before local speech | Retain current splitting, cost, and integration limits |
| 17 | Multi-Agent Workflow | A concrete task handoff and one writer per working copy | Retain; do not turn it into a study-tool dependency |
| 18 | Journal Article Transcription | Search inside a paper; reused extraction and task-card workflow | Link discovery and shared index; remove dangling price-comparison aside |
| 19 | Academic Hub | A question leading to sources and a study explanation | Make the shared foundation and outcome choices explicit |
| 20 | Normality Test | Structured departures from a bell curve and mixed simulation results | Retain standalone research scope |
| 21 | Wheat Yield Prediction | Accessible satellite data versus stronger field-data predictions | Retain standalone research scope |
| 22 | Socratic Tutor | Recorded learner progress and the restraint/teaching tension | Link one-off feedback and authored solution workflow |
| 23 | Corpus Health | On-disk text versus current search passages | Explain why study tools need the maintenance check |
| 24 | Project Steering | Explained priorities and stale proposals | Connect its trial-review example to Corpus Health |
| 25 | Study Guide Pipeline | Source selection and a requested section that missed its topic | Explain indexed input and map as a parallel output |
| 26 | Summary Enhancement | Reasoning and computed examples beyond a short result | Name valid starting documents and exact-passage reuse |
| 27 | AI Research Assistant | Locally scored abstracts and a specific research question | Link shared search, sourced answers, and course collection |
| 28 | Introducing Academic Hub | Original source-trail goal and first working converter | Retain historical perspective |
| 29 | Concept Graph | Conditions on arrows, illustrated by partial/total order | Link shared source preparation and guide alternative |
| 30 | Guided Solutions | Keeping student, agent, and tutoring contributions separate | Link source preparation and search |
| 31 | Managing this site | Editable text, inspectable changes, and theme module boundaries | Retain dated personal account |
| 32 | Converting Academic Resources | Page references, figure descriptions, and notation recovery | Retain dated counts and repair update |
| 33 | Textbook Conversion in Batches | Reuse despite renames and the cost of duplicate conversion | Retain |
| 34 | Indexing and Querying | Course/document/passage funnel and source diversity | Retain early-milestone framing |
| 35 | Tutor Hints | A useful direction and a solver blind to the earlier answer | Retain |
| 36 | Obsidian and Excalidraw | Automatic SVG output, editable plugins, handwriting comparison | Retain author's corrections |
| 37 | Finding Papers | Local abstract comparison and reviewed citation following | Retain dated access results |
| 38 | Academic Hub's Plumbing | History-size reduction and identity across moves | Retain |

Three collection introductions now explain reader tasks and routes into the
overviews. The blog collection already provides a conventional post listing
and needed no new visible introduction. Browser review found that all four
collections still inherited a HugoBlox promotional description for search and
sharing. Page-specific summary fields now replace that text, verified against
the generated meta descriptions. Titles, dates, filters, and design are
unchanged. No uniform section template or unrelated ecosystem links were
imposed on the independent projects.

## Verification and remaining work

Source checks passed for all 38 pages: original frontmatter preserved, all
29 image briefs preserved in position, 31 featured assets retained, and local
body-link destinations resolve. There are 40 new directed page-to-page links
in the substantive prose, with no prior body links removed. The count describes
navigation coverage, not writing quality; the contextual sentences supply
the explanation of each relationship.

The final production build passed with Hugo Extended 0.163.3 and pnpm 10.14.0
via Corepack: 119 Hugo pages, with 38 pages indexed by Pagefind. All 38 article
descriptions match their source summaries, new body links appear in production
HTML and resolve locally, and briefs stay out of the listings. The four
collection descriptions match their new page-specific summaries.

All 46 final browser records passed at 390-pixel mobile and 1440-pixel desktop
widths: nineteen changed article pages and four collections, with no missing
image requests, horizontal overflow, or runtime exceptions. Checked local
links returned HTTP 200. The missing first-image assets still render as theme
placeholder cards; absence of a broken image request does not mean those
thumbnails are finished. Screenshots were inspected along the principal
reader paths and on the project collections, including selected desktop views.

One initial RAG desktop screenshot was unstyled during concurrent preview/build
activity, despite passing the first helper's article-local checks. Its cause
was not established as a production defect. The evidence was retained, the
helper now waits for local stylesheets, and both RAG viewports were repeated
after builds settled. Stylesheets returned HTTP 200, the final layout was
visually checked, and the failed capture is excluded from the final passing
records. No website layout or configuration change was made for that finding.

Before snapshots and machine-readable evidence are preserved under
`.agent-reports/readability-holistic-review/`. The template-description finding
and unstyled initial preview have separate local reports under
`.agent-reports/bugs/20261016-holistic-collection-descriptions/` and
`.agent-reports/bugs/20261016-holistic-unstyled-preview/`. External link
availability and pipeline accuracy were not independently revalidated here.

Author judgment of voice, emphasis, and technical depth remains valuable.
The seven first images still need assets; 22 replacement briefs need review,
and every visible image placeholder must be removed before publication.
Some retained technical posters remain too dense to carry the new explanations
at thumbnail size. The image pass should make the shared foundation and
parallel study outputs legible rather than draw a single automatic pipeline.
No images, pipeline accuracy trials, learning studies, or new live integrated
runs were produced here. Nothing has been merged, pushed, or deployed.
