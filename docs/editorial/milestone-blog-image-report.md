# Retrospective Milestone Blog Image Generation Report

> **Final integration review, October 19:** Candidate 02 for all three remaining posts passed visual and factual review. The images are integrated as `featured.png` with explanatory captions and alt text on `codex/milestone-blog-final-publication`. All five retrospective posts are now prepared with `draft: false`; the three newly prepared posts will remain off the live site until this branch is merged and deployed. The earlier candidate status and Gemini handoff below are preserved as a record of what was reviewed.

> **Publication review, October 19:** Two images passed visual/factual review and were integrated into their page bundles on `codex/milestone-blog-publication-review` (commit `f9bea62`): `resume_parser_milestone` and `reviewable_study_guides`. The other three posts required targeted replacements per [the correction handoff](milestone-blog-image-corrections.md): `practice_problem_checks` removed incoherent algebra in favor of a clean architectural request/solution split; `questions_in_lecture_notes` replaced an overbroad convexity question and invented citation with an uncontroversial rate-of-change question and citation-free answer cards; `concept_map_conditions` replaced the specific unverified chapter/page citation with a generic "Source reference to review" badge while preserving the comparability condition and "Proposed" tag. All original `candidate-01.png` files are strictly preserved alongside the new `candidate-02.png` assets.

**Date:** 2026-10-19  
**Branch:** `gemini/milestone-blog-image-corrections`  
**Worktree:** `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-milestone-blog-image-corrections`  
**Status:** **Three replacement candidates generated and prepared for review** (Preserved under `image-candidates/`; not integrated into page bundles; drafts remain `draft: true` and `[[Insert Image: ...]]` briefs are preserved).

This report documents the initial candidates and subsequent revised candidates generated for Aaron Scherf's retrospective milestone blog drafts, following the requirements and briefs established in [`docs/editorial/milestone-blog-drafts.md`](milestone-blog-drafts.md), [`docs/editorial/milestone-blog-image-corrections.md`](milestone-blog-image-corrections.md), and each post's frontmatter.

All candidates were generated using Antigravity's native image-generation capability under subscription. No metered third-party API was invoked. All compositions adhere to the established restrained palette (dark navy `#14202D`, teal `#35C9C8`, and muted violet `#A58AE0`).

---

## Candidate Summary Table

| # | Post Slug | Post Title & Path | Candidate Path | Dimensions | File Size | SHA-256 Digest | Review Status |
|---|---|---|---|---|---|---|---|
| 1a | `practice_problem_checks` | [A Practice Problem Can Have the Right Answer...](../../content/blog/practice_problem_checks/index.md) | [`docs/editorial/image-candidates/practice_problem_checks/candidate-01.png`](image-candidates/practice_problem_checks/candidate-01.png) | 1376 x 768 (16:9) | 768,065 B | `1c06f46a027d0eb48e3e1ed114c46c7e287221f1008b0813082a034ef235d116` | **Superseded by Candidate 02** (incoherent algebra) |
| 1b | `practice_problem_checks` | [A Practice Problem Can Have the Right Answer...](../../content/blog/practice_problem_checks/index.md) | [`docs/editorial/image-candidates/practice_problem_checks/candidate-02.png`](image-candidates/practice_problem_checks/candidate-02.png) | 1376 x 768 (16:9) | 803,337 B | `aa74157487a546625daffd6d239bc195b1ba3108ff411998fb9b66ffb18d2cdc` | **Current review candidate** |
| 2 | `resume_parser_milestone` | [The Resume Step That Became Faster When I Removed the AI](../../content/blog/resume_parser_milestone/index.md) | [`docs/editorial/image-candidates/resume_parser_milestone/candidate-01.png`](image-candidates/resume_parser_milestone/candidate-01.png) | 1376 x 768 (16:9) | 736,783 B | `7b8aed3d2d1d9eeb70672a2c7183bdd257a1c252e64125884da0ce072c036077` | **Integrated in Codex branch** (`featured.png`) |
| 3a | `questions_in_lecture_notes` | [Giving the Questions in My Lecture Notes Somewhere to Go](../../content/blog/questions_in_lecture_notes/index.md) | [`docs/editorial/image-candidates/questions_in_lecture_notes/candidate-01.png`](image-candidates/questions_in_lecture_notes/candidate-01.png) | 1376 x 768 (16:9) | 668,641 B | `ccd2bbdb348322e2e95554389f48effac75884607152a57ddc40bbc4d82d88d9` | **Superseded by Candidate 02** (unverified citation & overbroad math) |
| 3b | `questions_in_lecture_notes` | [Giving the Questions in My Lecture Notes Somewhere to Go](../../content/blog/questions_in_lecture_notes/index.md) | [`docs/editorial/image-candidates/questions_in_lecture_notes/candidate-02.png`](image-candidates/questions_in_lecture_notes/candidate-02.png) | 1376 x 768 (16:9) | 656,444 B | `a9904a59dcaa38d8a20ac55a42f584bb6cf397c1b8c0b212e1349614b7b8d381` | **Current review candidate** |
| 4 | `reviewable_study_guides` | [A Long Study Guide Still Needs to Answer the Right Questions](../../content/blog/reviewable_study_guides/index.md) | [`docs/editorial/image-candidates/reviewable_study_guides/candidate-01.png`](image-candidates/reviewable_study_guides/candidate-01.png) | 1376 x 768 (16:9) | 836,470 B | `e2a82e7a70ce24572e5c48f1d962d6171b12d2e07e6f7e2cbdab23069d99a055` | **Integrated in Codex branch** (`featured.png`) |
| 5a | `concept_map_conditions` | [A Course Map Where the Arrows Have to Explain Themselves](../../content/blog/concept_map_conditions/index.md) | [`docs/editorial/image-candidates/concept_map_conditions/candidate-01.png`](image-candidates/concept_map_conditions/candidate-01.png) | 1376 x 768 (16:9) | 620,085 B | `37a74594052775cbc1614a897d1a539fae9250320fa6a2e54d583111b9a2c5c1` | **Superseded by Candidate 02** (unverified Section 1.2 citation) |
| 5b | `concept_map_conditions` | [A Course Map Where the Arrows Have to Explain Themselves](../../content/blog/concept_map_conditions/index.md) | [`docs/editorial/image-candidates/concept_map_conditions/candidate-02.png`](image-candidates/concept_map_conditions/candidate-02.png) | 1376 x 768 (16:9) | 537,057 B | `1a0d9bbd73f7c091c97c347a6f40fcbb6e84960afd7cf222fd4ca3d01a1a6595` | **Current review candidate** |

---

## Detailed Candidate Documentation

### 1. Practice Problem Checks: Separate Method & Soundness Verdicts

- **Page Bundle:** `content/blog/practice_problem_checks/index.md` (lines 20)
- **Candidate 01 (Preserved):** `docs/editorial/image-candidates/practice_problem_checks/candidate-01.png` (768,065 bytes, SHA-256: `1c06f46a027d0eb48e3e1ed114c46c7e287221f1008b0813082a034ef235d116`)
  - *Feedback:* Displayed incoherent pseudo-algebra steps that undermined example credibility.
- **Candidate 02 (Current Review):** `docs/editorial/image-candidates/practice_problem_checks/candidate-02.png`
  - **Tool / Method:** Antigravity `generate_image` (subscription native)
  - **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
  - **File Size:** 803,337 bytes
  - **SHA-256 Digest:** `aa74157487a546625daffd6d239bc195b1ba3108ff411998fb9b66ffb18d2cdc`
  - **Proposed Caption:** "A useful exercise has to practice the intended skill as well as reach a defensible answer."
  - **Proposed Alt Text:** "A practice request and draft solution branch to separate checks for requested method and sound reasoning, with the method check unresolved and the reasoning check noting review is still needed."
  - **Exact Generation Prompt:**
    ```text
    A clean modern technical editorial illustration on a solid dark navy background (#14202D) with vibrant teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal diagram layout. On the left, a rounded dark slate card displays a practice exercise titled 'Practice Request' with text 'Prove a result using the requested method', containing a neat container labelled 'Draft solution' with no displayed algebra or equations. From this card, two clean connector arrows branch to two separate evaluation cards on the right: Top card titled 'Requested method?' with an unresolved status badge '[ Unresolved ]' with a dashed border. Bottom card titled 'Sound reasoning?' with a badge '[ Model check: passed; review still needed ]'. High contrast flat vector editorial design, generous padding, crisp legible sans-serif typography, no pseudo-equations or fabricated math.
    ```
  - **Visual & Factual Checks:**
    - **No Fabricated Algebra:** Left card titled "Practice Request" features generic request text *"Prove a result using the requested method"* and a clean inner container *"Draft solution"* with completely blank interior space—zero incoherent algebraic steps or fabricated proofs.
    - **Separate Method Check:** Top check titled **"Requested method?"** contains a clear dashed badge `[ Unresolved ]` in muted violet.
    - **Separate Reasoning Check:** Bottom check titled **"Sound reasoning?"** displays the exact bracketed label `[ Model check: passed; review still needed ]`.
    - **Core Concept:** Directly illustrates that the two checks evaluate orthogonal criteria, that model checks are non-authoritative automated flags rather than correctness guarantees, and that human scrutiny remains essential.
    - **Legibility:** 100% accurate spelling, crisp sans-serif typography, high contrast, readable on mobile screens and at small thumbnail size.
    - **Review Status:** **Owner review pending** (Preserved under `image-candidates/`; not integrated into page bundle).

---

### 2. Resume Parser Milestone: Deterministic Field Mapping

- **Page Bundle:** `content/blog/resume_parser_milestone/index.md` (lines 20)
- **Candidate Path:** `docs/editorial/image-candidates/resume_parser_milestone/candidate-01.png`
- **Tool / Method:** Antigravity `generate_image` (subscription native)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 736,783 bytes
- **SHA-256 Digest:** `7b8aed3d2d1d9eeb70672a2c7183bdd257a1c252e64125884da0ce072c036077`
- **Publication Review Status:** **Approved and integrated** into `content/blog/resume_parser_milestone/featured.png` on branch `codex/milestone-blog-publication-review` (commit `f9bea62`).

---

### 3. Questions in Lecture Notes: Sourced vs. Unsourced Explanations

- **Page Bundle:** `content/blog/questions_in_lecture_notes/index.md` (lines 20)
- **Candidate 01 (Preserved):** `docs/editorial/image-candidates/questions_in_lecture_notes/candidate-01.png` (668,641 bytes, SHA-256: `ccd2bbdb348322e2e95554389f48effac75884607152a57ddc40bbc4d82d88d9`)
  - *Feedback:* Strict convexity question was mathematically overbroad; "Chapter 3, Page 42" was an unverified invented citation.
- **Candidate 02 (Current Review):** `docs/editorial/image-candidates/questions_in_lecture_notes/candidate-02.png`
  - **Tool / Method:** Antigravity `generate_image` (subscription native)
  - **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
  - **File Size:** 656,444 bytes
  - **SHA-256 Digest:** `a9904a59dcaa38d8a20ac55a42f584bb6cf397c1b8c0b212e1349614b7b8d381`
  - **Proposed Caption:** "An answer can be worth exploring while still needing a course source."
  - **Proposed Alt Text:** "A handwritten margin question connects to two possible saved-answer cards: one with course sources found explaining the local rate of change, and one noting a general explanation needs course checking."
  - **Exact Generation Prompt:**
    ```text
    A clean modern technical editorial illustration on a solid dark navy background (#14202D) with vibrant teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal diagram. On the left, a card titled 'Lecture Note' with a handwritten-style margin question: 'What does a derivative tell us here?'. Clean connector lines link to two possible saved-answer cards on the right. Top card has a teal badge 'Course sources found', bold text 'The course passage explains the local rate of change', and a small minimalist document icon with no chapter or page numbers. Bottom card has a muted violet badge 'Needs source checking', bold text 'A general explanation is available; course support still needed', with no citations or page numbers. High contrast flat vector aesthetic, crisp legible typography, no spelling errors.
    ```
  - **Visual & Factual Checks:**
    - **Uncontroversial Mathematical Note:** High-contrast left card titled "Lecture Note" features the margin question in clean handwritten script: *"What does a derivative tell us here?"*.
    - **Course Sourced Card:** Top card has a teal pill badge **"Course sources found"**, bold body text *"The course passage explains the local rate of change"*, and a clean minimalist document icon on the right side. Completely omits chapter, page numbers, or quotation text.
    - **Unsourced Explanation Card:** Bottom card has a muted violet pill badge **"Needs source checking"** and bold body text *"A general explanation is available; course support still needed"*. Contains zero citations or page numbers.
    - **Clear Visual Distinction:** Illustrates two *possible* saved outcomes without implying both were generated for a single question. Keeps note and answer cards visibly distinct.
    - **Legibility:** 100% accurate spelling, high contrast, crisp typography readable at mobile and thumbnail scale.
    - **Review Status:** **Owner review pending** (Preserved under `image-candidates/`; not integrated into page bundle).

---

### 4. Reviewable Study Guides: Assignment Checklist & Coverage Gap

- **Page Bundle:** `content/blog/reviewable_study_guides/index.md` (lines 20)
- **Candidate Path:** `docs/editorial/image-candidates/reviewable_study_guides/candidate-01.png`
- **Tool / Method:** Antigravity `generate_image` (subscription native)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 836,470 bytes
- **SHA-256 Digest:** `e2a82e7a70ce24572e5c48f1d962d6171b12d2e07e6f7e2cbdab23069d99a055`
- **Publication Review Status:** **Approved and integrated** into `content/blog/reviewable_study_guides/featured.png` on branch `codex/milestone-blog-publication-review` (commit `f9bea62`).

---

### 5. Concept Map Conditions: Illustrative Assumption on Connection

- **Page Bundle:** `content/blog/concept_map_conditions/index.md` (lines 20)
- **Candidate 01 (Preserved):** `docs/editorial/image-candidates/concept_map_conditions/candidate-01.png` (620,085 bytes, SHA-256: `37a74594052775cbc1614a897d1a539fae9250320fa6a2e54d583111b9a2c5c1`)
  - *Feedback:* "Source: Section 1.2, p. 14" was an unverified citation that risked appearing authoritative.
- **Candidate 02 (Current Review):** `docs/editorial/image-candidates/concept_map_conditions/candidate-02.png`
  - **Tool / Method:** Antigravity `generate_image` (subscription native)
  - **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
  - **File Size:** 537,057 bytes
  - **SHA-256 Digest:** `1a0d9bbd73f7c091c97c347a6f40fcbb6e84960afd7cf222fd4ca3d01a1a6595`
  - **Proposed Caption:** "The assumption belongs on the connection."
  - **Proposed Alt Text:** "A proposed connection from partial order to total order states that every pair must be comparable, with a generic source reference badge and a proposed status tag."
  - **Exact Generation Prompt:**
    ```text
    A clean modern technical editorial illustration on a solid dark navy background (#14202D) with vibrant teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal diagram of an illustrative concept graph connection. Two spacious dark slate concept cards sit on opposite sides: left card titled 'Partial order' with subtext 'Reflexive, transitive, antisymmetric'; right card titled 'Total order' with subtext 'Partial order with full comparability'. A prominent horizontal arrow connects Partial order to Total order. Directly attached to the arrow is a clear condition label 'Every pair can be compared', a generic badge 'Source reference to review', and a distinct status tag 'Proposed'. Clean flat vector graphic, crisp legible typography, generous spacing, illustrative diagram, no specific page or section numbers.
    ```
  - **Visual & Factual Checks:**
    - **Concept Cards:** Left card titled **"Partial order"** (reflexive, transitive, antisymmetric); right card titled **"Total order"** (partial order with full comparability). Both cards feature spacious margins and top accent bars (teal and violet).
    - **Connection & Condition:** Clean teal horizontal directional arrow connecting the two cards, with the condition box **"Every pair can be compared"** attached directly to the line.
    - **Generic Citation Marker:** Attached directly below the condition box is the generic badge **"Source reference to review"** (replacing the unverified Section 1.2, p. 14 text).
    - **Proposed Tag:** Muted violet pill badge **"Proposed"** preserved directly below the source reference tag.
    - **Evidentiary Meaning:** Accurately illustrates a single conceptual relation from the package's sample graph without implying the full course graph has been reviewed or that the citation guarantees mathematical proof.
    - **Legibility:** 100% accurate spelling, generous spacing, high contrast, readable on mobile screens and at small thumbnail size.
    - **Review Status:** **Owner review pending** (Preserved under `image-candidates/`; not integrated into page bundle).

---

## Workspace & Git Verification

1. **Worktree Isolation:** Work executed strictly in `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-milestone-blog-image-corrections` on branch `gemini/milestone-blog-image-corrections`.
2. **Page Bundles Unchanged:**
   - All three blog draft files under `content/blog/<slug>/index.md` remain unmodified (`draft: true`, `[[Insert Image: ...]]` briefs intact).
   - No `featured.png` or `featured.jpg` files were added to these three page bundles.
3. **Preservation:**
   - All `candidate-01.png` files are strictly preserved.
   - All `candidate-02.png` files are saved under `docs/editorial/image-candidates/<slug>/`.
4. **Explicit Staging:**
   - Staged explicitly using individual file paths:
     - `docs/editorial/image-candidates/practice_problem_checks/candidate-02.png`
     - `docs/editorial/image-candidates/questions_in_lecture_notes/candidate-02.png`
     - `docs/editorial/image-candidates/concept_map_conditions/candidate-02.png`
     - `docs/editorial/milestone-blog-image-report.md`
5. **No Merging / Pushing:**
   - No branches were merged, pushed, or deployed. Changes remain committed locally on `gemini/milestone-blog-image-corrections` awaiting owner review and publication handoff.
