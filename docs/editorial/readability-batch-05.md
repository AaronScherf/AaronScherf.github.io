# Readability revisions: batch 05

Prepared 2026-10-16. Scope: ten further project pages, starting from website
commit `9239250` on the owned `codex/readability-batch-01` branch/worktree.
Supporting monorepo: `7c2778c`. Source projects are read only. No project
pipelines, model calls, publication, or image generation are part of this pass.

The queue continues with guide entries 19, 18, 17, 16, 15, 14, 12, 11, 10,
and 9. Blog entries 13 and 28 remain deferred, following the established
project-page batch scope.

## Requirements and acceptance

| Requirement | Work and evidence | Status |
| --- | --- | --- |
| Revise ten pages | Pages listed below; keep each page's distinct purpose | Completed; pending author review |
| Substance near the opening | A supported mechanism, decision, example, or result in the first two prose paragraphs | Completed; briefs follow paragraph two |
| Accessible, human voice | Explain terms in context; retain interesting choices without hype or invented anecdotes | Pending author review |
| Check current context | Package/status/registry/lifecycle references and implementation where records differ | Completed; decisions below |
| Preserve scope | Original routes, dates, publication state, assets, and subproject metadata; summaries and captions reviewed | Metadata/source checks passed; summaries and captions updated |
| Image coverage | Existing featured image or visible image brief; specific replacement briefs where a more useful illustration is needed | Ten featured assets retained; ten replacement briefs added |
| Verify the website | Build, metadata/source/summary checks, twenty desktop/mobile browser records, screenshot inspection | Passed; twenty browser records and screenshot review completed |
| Preserve review stages | New prose, images, and publication remain separate decisions | Pending author review; no deployment |

## Page map

| Rank | Page | Main interest |
| --- | --- | --- |
| 19 | [Academic Hub](../../content/projects/academic-hub-overview/index.md) | A connected study scenario and task-based navigation, with validation limits beside the tools |
| 18 | [Journal Article Transcription](../../content/projects/ai-research-assistant/journal_article_transcription/index.md) | Search article contents with page locators; distinguish current agent task cards from the older API baseline |
| 17 | [Multi-Agent Workflow](../../content/projects/multi_agent_project/index.md) | Follow a website task through an isolated working copy and human integration |
| 16 | [Audio Generator](../../content/projects/academic-hub/audio_generator/index.md) | Turn formulas into speech and long notes into episodes; correct obsolete splitting claims |
| 15 | [Problem Corpus](../../content/projects/academic-hub/problem_corpus/index.md) | Preserve whether accompanying text is a student attempt; keep storage distinct from generator integration |
| 14 | [Notes Post-Processing](../../content/projects/academic-hub/postprocess_notes/index.md) | Catch a plausible-looking character error by comparing suspicious text with the source image |
| 12 | [Research Notes Conversion](../../content/projects/ai-research-assistant/research_notes_conversion/index.md) | Search Word research notes with papers and cite paragraphs when page references do not exist |
| 11 | [Obsidian Git Sync](../../content/projects/academic-hub/obsidian_git_sync/index.md) | Keep tablet notes lightweight, preserve app customization, and separate current configuration from retired approaches |
| 10 | [RAG Analysis](../../content/projects/academic-hub/rag_analysis/index.md) | A question, an answer illustration, and a reference to inspect; distinguish chat history from saved records |
| 9 | [Tutor Diagnosis](../../content/projects/academic-hub/tutor_diagnosis/index.md) | An attempt/hint/revision example plus a separate solution check and course-specific feedback |

## Sources and claim decisions

The [subproject registry](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/trackers/subproject_registry.json)
and page metadata supplied the package/status/lifecycle map. Those mappings
are preserved. The general routing and worktree documents are authoritative
for the workflow page. Relevant source paths checked here were clean in the
supporting checkout; unrelated source changes were not edited.

- **Overview:** groups all nineteen component links by reader task, using
  package READMEs and the previously reviewed project records. It removes
  outdated claims of local-only visualization, completed concept timestamps,
  or a bank already feeding generation. The opening scenario illustrates a
  connected workflow without claiming every step runs automatically.
- **Journal articles:** the
  [current README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/convert_journal_articles/README.md)
  and converter code supersede the older API-only account. The October 16
  [stage-1 plan](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/plans/literature_taxonomy/2026-10-16-stage1-journal-converter-driver.md)
  supplies lifecycle context absent from the old registry baseline. The task
  cards, explicit fallback, and separate indexing calls are implemented;
  the three-paper result is explicitly the older recorded trial, not a new
  agent-transcription accuracy evaluation. The historical price comparison
  is not presented as an accuracy comparison.
- **Multi-agent workflow:** the
  [routing guide](https://github.com/AaronScherf/ai-sandbox-master/blob/main/docs/AGENT_ROUTING.md)
  establishes Gemini's writing/pipeline role and explicit-assignment override.
  The [worktree procedure](https://github.com/AaronScherf/ai-sandbox-master/blob/main/docs/WORKTREE_WORKFLOW.md)
  establishes isolation and integration. The concrete website task is the
  workflow used for these revisions. The page removes universal product-memory
  claims and does not imply that another agent reviewed this batch.
- **Audio:** the
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/audio_generator/README.md)
  and `sections.py` include the October 10 paragraph-splitting fix (`9f609a1`).
  The page distinguishes that implemented fix from the
  [September live run](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/audio_generator/2026-09-09-audio-generator-status.md):
  3.8 minutes narration, 19.4 minutes speech synthesis, 23.2 total, nine
  episodes, including one about 62 minutes. A single indivisible paragraph
  remains a length exception. Whole-source regeneration, note/textbook output
  differences, and storage outside tablet sync follow the current README.
  Summary tools exist; an automatic weekly-summary-to-audio integration and
  improved learning from listening are not claimed. Formula speech is an
  explicitly illustrative example.
- **Problem bank:** the
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/problem_corpus/README.md)
  explicitly stops at stored output. The 196-record result is scoped to its
  eight-file run, not an accuracy audit. The invented even-integer question
  card contains no private coursework and does not label student work verified.
- **Post-processing:** the
  [status record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/postprocess_notes/2026-08-27-notes-postprocessing-status.md)
  supports the repaired square-root example, nine unchanged candidates,
  surrounding-context scoring, spacing errors, and false positives. The short
  formula comparison illustrates the recorded glyph issue without reproducing
  a private source page. Source-image comparison is a check with its own error
  possibilities, rather than a guarantee that false positives cannot corrupt text.
- **Word research notes:** the
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/pipelines/convert_essays/README.md)
  separates local conversion from optional API indexing. The
  [19-file record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/convert_essays/2026-09-01-research-notes-conversion-status.md)
  supports vocabulary, multi-collection identity, and paragraph fallback.
  The sample heading/locator is illustrative; no private essay is quoted.
  Drive ingestion is not described as part of the current converter.
- **Sync:** the author's automatic-export and plugin-customization corrections
  are retained. The September 26 Fit record supersedes the earlier tablet
  plugin, while the later entries in the
  [relocation plan](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/plans/convert_textbook/2026-09-21-source-asset-relocation.md)
  report the existing course sources moved on September 23. The old sync page
  incorrectly left that move as future work. The page distinguishes exported
  images from editable scenes, and manual plugin-code copies from syncable
  interface snippets. New files still depend on the configured paths and rules;
  no continuous source-migration service is claimed.
- **RAG:** the
  [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/agent/rag/README.md)
  and its linked status records support passage diversification, query
  reformulation, live-process history, course event logs, summaries, and the
  seven-question resolver result. The spectral-theorem question/sketch/reference
  is explicitly illustrative, not a private-source quote or an actual retrieved
  passage. Grounding, memory, and coverage limits remain visible.
- **Tutor diagnosis:** the
  [status](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/agent/rag/2026-09-27-tutor-diagnosis-status.md),
  README, and `tutor_diagnosis.py` support three feedback axes, general-hint
  fallback, blind second solving, and course logs. The even-integer exchange
  is invented and labelled illustrative. Historical regression/intercept
  examples stay scoped to their trials. Scores are not instructor grades and
  the checker supplies no automatic verdict. The separate Socratic Tutor is
  linked and distinguished.

## Validation and remaining work

Production build passed with Hugo Extended 0.163.3 and pnpm 10.14.0:
119 Hugo pages; Pagefind indexed 38 pages. Source checks passed for all ten
pages: original dates, routes, titles, tags, publication state, assets, and
subproject metadata preserved; `lastmod: 2026-10-16`, summaries, and captions
updated. Every image brief follows paragraph two and stays below the excerpt
marker. The prose is approximately 260–400 words per page excluding briefs.

Listing checks and the twenty-eight-page image inventory passed. Visual review
caught a separate source-writing error: a PowerShell pipe replaced non-ASCII
symbols with question marks before Python received them. Seven new texts were
affected, including the square-root illustration. The damaged files and initial
browser evidence were preserved; exact replacements using Unicode escapes
restored the intended characters. Source assertions now check every affected
symbol and allow only the two genuine question marks in the examples. The
production build passed after that correction, and the seven affected pages
were rechecked at both viewport sizes. Exact characters match in source,
production HTML, and browser text. The local bug record is preserved under
`.agent-reports/bugs/20261016-readability-unicode/`.

Final browser checks passed for all ten pages at 390-pixel mobile and
1440-pixel desktop widths: no missing images, article overflow, or runtime
exceptions; every local article link returned HTTP 200. All ten mobile
screenshots and selected desktop screenshots were inspected, including the
corrected formula table. The source, coverage, and final browser records are
preserved under `.agent-reports/readability-batch-05/`. These are website
rendering checks, not new evaluations of the described tools.

The cumulative scope is twenty-eight revised pages; ten guide entries remain,
including the two deferred blogs. Prose review, seven first-image assets,
twelve proposed replacements, and publication remain separate gates. No
project pipelines, performance benchmarks, or teaching trials were rerun.
