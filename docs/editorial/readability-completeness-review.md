# Readability completeness review

Prepared 2026-10-16. All 38 substantive entries in the revised editorial
guide now have revised text on `codex/readability-batch-01`: 28 project pages
and 10 blog posts. Nine unpublished template examples remain excluded.
This is a review inventory, not author approval or publication clearance.

## Current state

| Area | Evidence and remaining work |
| --- | --- |
| Queue coverage | All 38 guide URLs resolve to edited source files; no substantive entry remains undrafted |
| Original structure | Existing routes and publication states preserved; summaries and captions revised; the long audio-blog title shortened without changing its URL |
| Technical substance | Each batch records its supported opening detail and source decisions; the holistic editorial review now covers tone, depth, repeated claims, and reader paths |
| Images | 31 existing featured assets retained; 7 first-image briefs and 22 replacement briefs await the later image pass |
| Validation | Production build and source/listing checks passed for the final batch; browser results are recorded in batch 06 |
| Source navigation | Existing code/README/status mappings resolve locally; local body links resolve in the built site |
| Author decisions | Earlier review states remain in their batch records; no blanket final approval has been inferred |
| Publication | No merge, push, deployment, or application submission performed |

The original guide remains unchecked because its completion criteria include
author review and finished visuals. This website record tracks drafting
progress without changing owner decisions in the source repository.

## Full inventory

| Guide rank | Page | Visual handoff |
| --- | --- | --- |
| 01 | [Notes Transcription Pipeline](../../content/projects/academic-hub/notes_transcription/index.md) | replacement brief |
| 02 | [Marker PDF Conversion](../../content/projects/academic-hub/marker_conversion/index.md) | replacement brief |
| 03 | [Journal Discovery Pipeline](../../content/projects/ai-research-assistant/journal_discovery/index.md) | replacement brief |
| 04 | [Visualization Sub-Agent](../../content/projects/academic-hub/visualization/index.md) | replacement brief |
| 05 | [Source Indexer](../../content/projects/academic-hub/source_indexer/index.md) | replacement brief |
| 06 | [Resume Manager](../../content/projects/resume_manager/index.md) | replacement brief |
| 07 | [Video Lecture Notes](../../content/projects/academic-hub/video_notes/index.md) | replacement brief |
| 08 | [Problem Generation Sub-Agent](../../content/projects/academic-hub/problem_generation/index.md) | replacement brief |
| 09 | [Tutor Diagnosis & Hint Generator](../../content/projects/academic-hub/tutor_diagnosis/index.md) | replacement brief |
| 10 | [RAG Analysis](../../content/projects/academic-hub/rag_analysis/index.md) | replacement brief |
| 11 | [Obsidian Git Sync](../../content/projects/academic-hub/obsidian_git_sync/index.md) | replacement brief |
| 12 | [Research Notes Conversion](../../content/projects/ai-research-assistant/research_notes_conversion/index.md) | replacement brief |
| 13 | [Turning Dense Math Notes into Commute Podcasts](../../content/blog/audio_generator_podcasts/index.md) | replacement brief |
| 14 | [Notes Post-Processing](../../content/projects/academic-hub/postprocess_notes/index.md) | replacement brief |
| 15 | [Problem Corpus Extraction](../../content/projects/academic-hub/problem_corpus/index.md) | replacement brief |
| 16 | [Audio Generator](../../content/projects/academic-hub/audio_generator/index.md) | replacement brief |
| 17 | [Multi-Agent Development Workflow](../../content/projects/multi_agent_project/index.md) | replacement brief |
| 18 | [Journal Article Transcription](../../content/projects/ai-research-assistant/journal_article_transcription/index.md) | replacement brief |
| 19 | [Academic Hub](../../content/projects/academic-hub-overview/index.md) | replacement brief |
| 20 | [Novel Omnibus Normality Test](../../content/projects/math_thesis/index.md) | replacement brief |
| 21 | [Predicting Wheat Yields in New Environments](../../content/projects/wheat_yield_prediction/index.md) | replacement brief |
| 22 | [Socratic Tutor](../../content/projects/academic-hub/socratic_tutor/index.md) | first image needed |
| 23 | [Corpus Health](../../content/projects/academic-hub/corpus_health/index.md) | first image needed |
| 24 | [Project Steering](../../content/projects/academic-hub/project_steering/index.md) | first image needed |
| 25 | [Study Guide Pipeline](../../content/projects/academic-hub/study_guide_pipeline/index.md) | first image needed |
| 26 | [Summary Enhancement](../../content/projects/academic-hub/summary_enhancement/index.md) | first image needed |
| 27 | [AI Research Assistant](../../content/projects/ai-research-assistant-overview/index.md) | existing image retained |
| 28 | [Introducing Academic Hub](../../content/blog/academic_hub/index.md) | replacement brief |
| 29 | [Concept Graph](../../content/projects/academic-hub/concept_graph/index.md) | first image needed |
| 30 | [Guided Solutions](../../content/projects/academic-hub/guided_solutions/index.md) | first image needed |
| 31 | [Managing this site with HugoBlox and Claude](../../content/blog/site_management/index.md) | existing image retained |
| 32 | [Converting Academic Resources to Markdown](../../content/blog/academic_resource_progress/index.md) | existing image retained |
| 33 | [Making Textbook Conversion Easier to Run in Batches](../../content/blog/textbook_conversion_automation/index.md) | existing image retained |
| 34 | [Indexing and Querying Academic Hub](../../content/blog/indexer_and_rag_progress/index.md) | existing image retained |
| 35 | [An AI Tutor That Gives Hints and Checks Your Reasoning](../../content/blog/pedagogical_rag_hints/index.md) | existing image retained |
| 36 | [Why I Use Obsidian and Excalidraw for Academic Notes](../../content/blog/obsidian_excalidraw_notes/index.md) | existing image retained |
| 37 | [Finding Academic Papers for a Research Library](../../content/blog/academic_journal_discovery/index.md) | existing image retained |
| 38 | [Tidying Up Academic Hub's Plumbing](../../content/blog/academic_hub_infrastructure_cleanup/index.md) | existing image retained |

## Review next

The [holistic portfolio review](readability-holistic-review.md) records the
full-set assessment and focused follow-up changes, including links between
source preparation, search, summaries, guides, and concept maps. Author
review and the visual pass remain open.

Read the site as a connected portfolio: whether each opening explains a
useful idea, whether technical detail is specific enough, and whether similar
projects remain distinguishable. Check the dated blogs against the current
project pages without erasing their historical perspective. Review new
first-person passages for the author's actual voice and experience.

The image pass must create the seven missing featured assets, assess the
22 proposed replacements, apply captions and alt text, and remove every
`Insert Image` block. Mathematical plots and thesis figures need actual
outputs or standard plotting tools rather than invented scientific artwork.
Check the resulting article images and thumbnail crops at mobile and desktop
widths. A brief alone cannot produce a thumbnail.

Website rendering checks do not revalidate conversion accuracy, generated
mathematics, job-application claims, learning outcomes, or long-term pipeline
reliability. Those remain limited to the evidence cited on the pages.

The optional source website-sync auditor could not start because its existing
virtual environment lacks `jsonschema`; no dependencies were installed.
Direct checks of preserved subproject paths and built local-link targets
passed. This narrower check does not replace the auditor's Git/lifecycle
comparison or a fresh review of every external link.

See [batch 06](readability-batch-06.md) for the final ten pages,
[the visual handoff](readability-visual-handoff.md) for image instructions,
and [detail calibration](readability-detail-calibration.md) for the
author's requested balance between accessibility and technical interest.
