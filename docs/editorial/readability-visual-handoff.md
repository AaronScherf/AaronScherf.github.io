# Featured-image coverage and generation handoff

Prepared 2026-10-16 after the author clarified that every page needs an image
for its thumbnail. No new image assets have been generated in this pass.

## Requirement for remaining batches

Every revised page must retain a suitable existing featured image or contain
a visible `[[Insert Image: Description]]` brief for the later Gemini pass.
The image should explain something substantive about the project, with a
composition that also works at thumbnail size. Use a few large labels and
readable mobile text. Keep private notes and coursework out of the image.

Put a needed image brief after the first or second substantive paragraph,
below the `<!--more-->` marker so it stays out of automatic excerpts. Include
the composition, its explanatory purpose, suggested caption and alt text,
and the eventual `featured.jpg` or `featured.png` page-bundle asset. Existing
images satisfy the minimum; extra visuals should have a clear purpose.

This requirement supplements the revised readability guide and supersedes
its optional-visual rule. Earlier passes preserved images but did not require
image coverage, leaving four project pages without an image or brief. The
author requested descriptions for later generation; generating the assets
remains a separate step.

## Thirteen revised pages

| Page | Current coverage | Remaining visual work |
| --- | --- | --- |
| [Obsidian and Excalidraw](../../content/blog/obsidian_excalidraw_notes/index.md) | Existing `featured.jpg` retained | Small labels can be improved later |
| [Finding Academic Papers](../../content/blog/academic_journal_discovery/index.md) | Existing `featured.jpg` retained | Existing image retained |
| [Academic Hub's Plumbing](../../content/blog/academic_hub_infrastructure_cleanup/index.md) | Existing `featured.jpg` retained | Existing image retained |
| [Managing this site](../../content/blog/site_management/index.md) | Existing `featured.jpg` retained | Existing image retained |
| [Converting Academic Resources](../../content/blog/academic_resource_progress/index.md) | Existing `featured.jpg` retained | Existing image retained |
| [Textbook Conversion in Batches](../../content/blog/textbook_conversion_automation/index.md) | Existing `featured.jpg` retained | Existing image retained |
| [Indexing and Querying Academic Hub](../../content/blog/indexer_and_rag_progress/index.md) | Existing `featured.jpg` retained | Existing image retained |
| [Tutor Hints and Reasoning Checks](../../content/blog/pedagogical_rag_hints/index.md) | Existing `featured.jpg` retained | Existing image retained |
| [AI Research Assistant](../../content/projects/ai-research-assistant-overview/index.md) | Existing `featured.jpg` retained | Small labels can be improved later |
| [Guided Solutions](../../content/projects/academic-hub/guided_solutions/index.md) | New visible brief after paragraph two | Generate three-contribution illustration; add featured asset |
| [Concept Graph](../../content/projects/academic-hub/concept_graph/index.md) | New visible brief after paragraph two | Generate conditional-connection diagram; add featured asset |
| [Summary Enhancement](../../content/projects/academic-hub/summary_enhancement/index.md) | New visible brief after paragraph two | Generate summary-to-explanation illustration; add featured asset |
| [Study Guide Pipeline](../../content/projects/academic-hub/study_guide_pipeline/index.md) | New visible brief after paragraph two | Generate source/draft/review/revised-copy illustration; add featured asset |

The nine existing assets were preserved, not redesigned. The four descriptions
are in the page Markdown itself, not hidden in comments or metadata.

## Later Gemini image pass

Use each page's `Insert Image` block as the brief. Check the result against
the page's actual behavior and review its labels for accuracy. Save the
approved image in that page's bundle, apply its caption and alt text, and
remove the entire placeholder block. A description alone cannot supply a
thumbnail; do not add an empty image path or a broken image link.

Build the site and inspect the article and its collection card at desktop
and mobile widths. The four missing images should appear in the Academic Hub
subproject collection. Thumbnail generation, cropping, and legibility remain
unverified until those assets exist. Publication waits for those images,
placeholder removal, and the author's content approval.

## Validation of this correction

- Coverage passed for all thirteen revised pages: nine retained featured
  assets and four visible source briefs. All four briefs follow paragraph
  two, below the excerpt marker, and include captions, alt text, and filenames.
- Production build passed with Hugo Extended 0.163.3; Pagefind indexed 38 pages.
- Generated HTML contains each brief as a visible paragraph. Descriptions
  remain unchanged, and the Academic Hub collection excerpts contain no briefs.
- No assets were generated and no new image links were introduced. Image
  generation, thumbnail appearance, and author review of the briefs remain
  pending. No new browser screenshot review was performed for this text-only
  correction; the actual images must be checked when they exist.

The local mismatch report and before snapshots are preserved under
`.agent-reports/bugs/20261016-missing-figure-briefs/`. The author is the proposed
reviewer for visual direction; no external reviewer has been contacted.
