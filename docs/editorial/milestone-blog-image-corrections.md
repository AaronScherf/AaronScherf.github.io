# Corrections for the three remaining milestone blog images

Use the clean Gemini candidate branch as the source of the three existing images and the current Codex publication-review branch for the post text. Make replacement images as `candidate-02.png` alongside each `candidate-01.png`; keep the originals for comparison. Work in a dedicated Gemini branch/worktree and do not change post frontmatter, remove image briefs, or publish. Show the replacement images and an updated factual/visual review before integration.

Maintain the established editorial style: 16:9 landscape composition, dark navy background, teal and muted violet accents, legible short labels at mobile size, restrained diagram style, and no private material or imitation of a real product screen. Each image is an **illustration**, not a record of an actual run. Avoid invented course citations, page numbers, and mathematical steps that have not been checked.

## `practice_problem_checks`

The first candidate's pseudo-equations are incoherent and make the example less trustworthy. Retain the useful visual structure of one practice request branching to two separate checks. Use a generic request such as **“Prove a result using the requested method”** and a solution card labelled **“Draft solution”**, with no displayed algebra or fabricated proof. The checks should ask **“Requested method?”** and **“Sound reasoning?”**. Show the method check as **unresolved** and the reasoning result, if shown, as **“Model check: passed; review still needed”**. Do not turn a model verdict into a correctness guarantee. The page's point is that the checks can disagree and need independent human scrutiny.

## `questions_in_lecture_notes`

The first candidate's strict-convexity question and its supposed answers are mathematically overbroad, while “Chapter 3, Page 42” looks like a real source citation that was never verified. Use a simple invented note question with an uncontroversial explanation, for example **“What does a derivative tell us here?”**. Draw two *possible* saved-answer cards: **“Course sources found”** with **“The course passage explains the local rate of change”**, and **“Needs source checking”** with **“A general explanation is available; course support still needed”**. A small source-document icon is fine on the first card; do not put a chapter, page, or quotation on either card. Keep the question and answer visibly separate. Do not imply both cards were produced for one real question in the seven-question run.

## `concept_map_conditions`

The partial-order to total-order relationship and the comparability condition are useful and mathematically sound. Preserve those elements and the **“Proposed”** tag. Replace **“Source: Section 1.2, p. 14”** with a generic **“Source reference to review”** badge or a document icon, because that specific citation has not been verified. The image should not imply that a source reference verifies the mathematics or that the full course graph has been reviewed.

## Acceptance checks

- Inspect each rendered image at its original resolution and a small thumbnail size. Confirm every visible word, equation, arrow, and citation is accurate and legible.
- Keep each candidate outside `content/` until approved; report its dimensions and path.
- Do not overwrite or delete the first candidates.
- Hand off the three replacements for integration. The publication review will then recheck the matched post and image together, add a `featured.png`, alt text and caption, remove its `[[Insert Image: ...]]` brief, and decide its `draft` state.
