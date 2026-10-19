# Retrospective Milestone Blog Image Generation Report

**Date:** 2026-10-19  
**Branch:** `gemini/milestone-blog-images`  
**Worktree:** `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-milestone-blog-images`  
**Status:** **All 5 candidate images generated and prepared for owner review** (Awaiting explicit owner approval before page bundle integration; drafts remain `draft: true` and `[[Insert Image: ...]]` briefs are preserved).

This report documents the five image candidates generated for Aaron Scherf's retrospective milestone blog drafts, following the requirements and briefs established in [`docs/editorial/milestone-blog-drafts.md`](milestone-blog-drafts.md) and each post's frontmatter and `[[Insert Image: ...]]` section.

All candidates were generated using Antigravity's native image-generation capability under subscription. No metered third-party API was invoked. All compositions adhere to the established restrained palette (dark navy `#14202D`, teal `#35C9C8`, and muted violet `#A58AE0`) with distinct conceptual layouts tailored to each post's specific technical decision.

---

## Candidate Summary Table

| # | Post Slug | Post Title & Path | Candidate Path | Dimensions | File Size | SHA-256 Digest | Review Status |
|---|---|---|---|---|---|---|---|
| 1 | `practice_problem_checks` | [A Practice Problem Can Have the Right Answer and Still Miss the Point](../../content/blog/practice_problem_checks/index.md) | [`docs/editorial/image-candidates/practice_problem_checks/candidate-01.png`](image-candidates/practice_problem_checks/candidate-01.png) | 1376 x 768 (16:9) | 768,065 B | `1c06f46a027d0eb48e3e1ed114c46c7e287221f1008b0813082a034ef235d116` | **Pending owner review** |
| 2 | `resume_parser_milestone` | [The Resume Step That Became Faster When I Removed the AI](../../content/blog/resume_parser_milestone/index.md) | [`docs/editorial/image-candidates/resume_parser_milestone/candidate-01.png`](image-candidates/resume_parser_milestone/candidate-01.png) | 1376 x 768 (16:9) | 736,783 B | `7b8aed3d2d1d9eeb70672a2c7183bdd257a1c252e64125884da0ce072c036077` | **Pending owner review** |
| 3 | `questions_in_lecture_notes` | [Giving the Questions in My Lecture Notes Somewhere to Go](../../content/blog/questions_in_lecture_notes/index.md) | [`docs/editorial/image-candidates/questions_in_lecture_notes/candidate-01.png`](image-candidates/questions_in_lecture_notes/candidate-01.png) | 1376 x 768 (16:9) | 668,641 B | `ccd2bbdb348322e2e95554389f48effac75884607152a57ddc40bbc4d82d88d9` | **Pending owner review** |
| 4 | `reviewable_study_guides` | [A Long Study Guide Still Needs to Answer the Right Questions](../../content/blog/reviewable_study_guides/index.md) | [`docs/editorial/image-candidates/reviewable_study_guides/candidate-01.png`](image-candidates/reviewable_study_guides/candidate-01.png) | 1376 x 768 (16:9) | 836,470 B | `e2a82e7a70ce24572e5c48f1d962d6171b12d2e07e6f7e2cbdab23069d99a055` | **Pending owner review** |
| 5 | `concept_map_conditions` | [A Course Map Where the Arrows Have to Explain Themselves](../../content/blog/concept_map_conditions/index.md) | [`docs/editorial/image-candidates/concept_map_conditions/candidate-01.png`](image-candidates/concept_map_conditions/candidate-01.png) | 1376 x 768 (16:9) | 620,085 B | `37a74594052775cbc1614a897d1a539fae9250320fa6a2e54d583111b9a2c5c1` | **Pending owner review** |

---

## Detailed Candidate Documentation

### 1. Practice Problem Checks: Separate Method & Soundness Verdicts

- **Page Bundle:** `content/blog/practice_problem_checks/index.md` (lines 20)
- **Candidate Path:** `docs/editorial/image-candidates/practice_problem_checks/candidate-01.png`
- **Tool / Method:** Antigravity `generate_image` (subscription native)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 768,065 bytes
- **SHA-256 Digest:** `1c06f46a027d0eb48e3e1ed114c46c7e287221f1008b0813082a034ef235d116`
- **Proposed Caption:** "A useful exercise has to practice the intended skill as well as reach a defensible answer."
- **Proposed Alt Text:** "A practice solution faces separate checks for its requested method and the soundness of its reasoning."
- **Exact Generation Prompt:**
  ```text
  A clean modern technical editorial illustration on a solid dark navy background (#14202D) with vibrant teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal layout representing two separate checks for a generated exercise. On the left, a rounded dark slate card titled 'Practice Solution' with clean minimal mathematical steps: 'Problem: Show linear independence' and brief algebraic steps. From this solution card, two clean connector arrows branch to two separate evaluation cards on the right: Top card titled 'Requested method?' featuring an unresolved, pending status badge 'Unresolved' with a neutral dashed border, noting 'Requested technique check pending'. Bottom card titled 'Sound reasoning?' with a badge 'Model check: Steps valid' accompanied by a small disclaimer tag 'Automated feedback (not proof of correctness)'. High contrast, flat vector editorial design, generous padding, crisp legible typography suitable for mobile screens.
  ```
- **Visual & Factual Checks:**
  - **Core Concept:** Visually demonstrates the architectural split between checking mathematical soundness and verifying adherence to the requested problem-solving technique.
  - **Left Card:** Titled "Practice Solution" containing clean, minimal invented steps for showing linear independence ($a=2+b=0$, $+x=2x+b=1$, $x=0$).
  - **Top Check:** Clearly titled "Requested method?" with a dashed, unresolved badge `[ Unresolved ]` and label `Requested technique check pending`. Avoids false green approval ticks.
  - **Bottom Check:** Titled "Sound reasoning?" featuring a teal pill `[ Model check: Steps valid ]` accompanied by an explicit disclaimer pill: `[ Automated feedback (not proof of correctness) ]`. This prevents model feedback from being mistaken for mathematical proof of correctness.
  - **Typography & Layout:** Crisp sans-serif fonts, flawless spelling across all cards and badges, generous padding, readable on mobile screens and recognizable at thumbnail size.
  - **Review Status:** **Owner review pending** (Preserved under `image-candidates/`; not integrated into page bundle).

---

### 2. Resume Parser Milestone: Deterministic Field Mapping

- **Page Bundle:** `content/blog/resume_parser_milestone/index.md` (lines 20)
- **Candidate Path:** `docs/editorial/image-candidates/resume_parser_milestone/candidate-01.png`
- **Tool / Method:** Antigravity `generate_image` (subscription native)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 736,783 bytes
- **SHA-256 Digest:** `7b8aed3d2d1d9eeb70672a2c7183bdd257a1c252e64125884da0ce072c036077`
- **Proposed Caption:** "Keep the facts in named fields before changing the emphasis."
- **Proposed Alt Text:** "A generic resume maps employer, role, location, and dates into separate fields, while bullet wording remains separately editable."
- **Exact Generation Prompt:**
  ```text
  A clean modern technical editorial illustration on a solid dark navy background (#14202D) with vibrant teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal layout emphasizing structured data extraction from a resume. On the left, a rounded dark card 'Resume Source' with invented text: 'Apex Analytics', 'Research Analyst', 'Denver, CO', '2022-2024'. Clean connector lines map each item into a central card 'Structured Master Record' with four distinct labelled fields: 'Employer: Apex Analytics', 'Role: Research Analyst', 'Location: Denver, CO', and 'Dates: 2022-2024'. Separated to the right, a distinct card 'Editable Bullet Wording' displays a bullet point with an edit pencil symbol: '• Analyzed regional pricing datasets', with a subtitle 'Editable phrasing kept separate from fixed fields'. High contrast flat vector aesthetic, crisp legible typography, no speed charts or benchmarks.
  ```
- **Visual & Factual Checks:**
  - **Core Concept:** Focuses on deterministic parsing mapping unstructured resume text into four named fields, keeping factual identity strictly separate from language generation and bullet tailoring.
  - **Source Card:** Card titled "Resume Source" with four clean invented items: `Apex Analytics`, `Research Analyst`, `Denver, CO`, and `2022-2024`. Contains no real private contact details or personal history.
  - **Master Record:** Central card titled "Structured Master Record" with four distinct, neatly aligned target fields: `Employer: Apex Analytics`, `Role: Research Analyst`, `Location: Denver, CO`, and `Dates: 2022-2024`, linked by individual connector lines with anchor points.
  - **Detached Bullet Card:** Separated right-side card titled "Editable Bullet Wording" showing a pencil edit icon, an editable sample bullet (`• Analyzed regional pricing datasets`), and explicit explanatory text: `Editable phrasing kept separate from fixed fields`.
  - **Negative Constraint Check:** Completely avoids speed charts, benchmark bars, or performance graphs, keeping the focus entirely on structural schema separation.
  - **Review Status:** **Owner review pending** (Preserved under `image-candidates/`; not integrated into page bundle).

---

### 3. Questions in Lecture Notes: Sourced vs. Unsourced Explanations

- **Page Bundle:** `content/blog/questions_in_lecture_notes/index.md` (lines 20)
- **Candidate Path:** `docs/editorial/image-candidates/questions_in_lecture_notes/candidate-01.png`
- **Tool / Method:** Antigravity `generate_image` (subscription native)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 668,641 bytes
- **SHA-256 Digest:** `ccd2bbdb348322e2e95554389f48effac75884607152a57ddc40bbc4d82d88d9`
- **Proposed Caption:** "An answer can be worth exploring while still needing a course source."
- **Proposed Alt Text:** "A handwritten question leads to a separate answer, with distinct labels for course-supported explanations and explanations that need source checking."
- **Exact Generation Prompt:**
  ```text
  A clean modern technical editorial illustration on a solid dark navy background (#14202D) with vibrant teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal diagram. On the left, a white card with heading 'Lecture Notes' contains a handwritten margin question: '? Why does strict convexity imply a unique optimum?'. Clean connector lines fork into two separate cards on the right. Top card has a teal badge 'Course sources found', bold text 'Confirmed in course notes: single tangency point.', and a pill tag 'Source: Chapter 3, Page 42'. Bottom card has a violet badge 'Needs source checking', bold text 'General intuition: strictly diminishing MRS prevents multiple bundles.', and a pill tag 'Explanation awaiting course support' (no source citation). High contrast, flat graphic design, legible typography, no spelling errors.
  ```
- **Visual & Factual Checks:**
  - **Core Concept:** Captures the question resolver's critical evidentiary distinction between explanations grounded in indexed course materials versus general explanations awaiting course backing.
  - **Left Card:** High-contrast white card titled "Lecture Notes" featuring a clean handwritten-style script question: `? Why does strict convexity imply a unique optimum?`.
  - **Top Card (Sourced):** Labelled with a teal pill badge `Course sources found`. Body text states: `Confirmed in course notes: single tangency point.` Accompanied by a clear source marker pill: `Source: Chapter 3, Page 42`.
  - **Bottom Card (Unsourced Explanation):** Labelled with a muted violet badge `Needs source checking`. Body text provides the actual explanation: `General intuition: strictly diminishing MRS prevents multiple bundles.` Explicitly tagged with `Explanation awaiting course support`. Completely omits source-page citations. Depicts an explanation waiting for course support, rather than an unanswered question or an unverified blank card.
  - **Review Status:** **Owner review pending** (Preserved under `image-candidates/`; not integrated into page bundle).

---

### 4. Reviewable Study Guides: Assignment Checklist & Coverage Gap

- **Page Bundle:** `content/blog/reviewable_study_guides/index.md` (lines 20)
- **Candidate Path:** `docs/editorial/image-candidates/reviewable_study_guides/candidate-01.png`
- **Tool / Method:** Antigravity `generate_image` (subscription native)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 836,470 bytes
- **SHA-256 Digest:** `e2a82e7a70ce24572e5c48f1d962d6171b12d2e07e6f7e2cbdab23069d99a055`
- **Proposed Caption:** "Check the guide against what it is meant to help you do."
- **Proposed Alt Text:** "An assignment checklist matches two guide sections while a third requirement reveals a coverage gap, despite a reviewed edit elsewhere."
- **Exact Generation Prompt:**
  ```text
  A clean modern technical editorial illustration on a solid dark navy background (#14202D) with vibrant teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal comparison layout. On the left, a rounded dark slate card titled 'Assignment Checklist' listing three items: '1. Utility Maximization', '2. Slutsky Symmetry', and '3. Duality & Expenditure'. On the right, a card titled 'Study Guide Draft' containing: top section 'Section 1: Utility Maximization' with a small violet badge 'Reviewed edit applied', and middle section 'Section 2: Slutsky Symmetry'. Clean connector lines link items 1 and 2 to their respective sections. Item 3 leads to an empty dashed placeholder box prominently labelled with a warning badge 'Coverage gap'. Bottom caption pill: 'Reviewed edits do not ensure full assignment coverage'. Crisp typography, high contrast flat vector aesthetic.
  ```
- **Visual & Factual Checks:**
  - **Core Concept:** Demonstrates that a lengthy study guide with reviewed section edits can still have unaddressed gaps when evaluated against an assignment checklist.
  - **Left Card:** "Assignment Checklist" listing three discrete requirements: `1. Utility Maximization`, `2. Slutsky Symmetry`, and `3. Duality & Expenditure`.
  - **Right Card:** "Study Guide Draft" displaying `Section 1: Utility Maximization` (with a violet badge `Reviewed edit applied`) and `Section 2: Slutsky Symmetry`, both connected with teal arrows.
  - **Coverage Gap:** Requirement 3 (`3. Duality & Expenditure`) points directly across to an empty dashed container containing an alert pill: `⚠ Coverage gap`.
  - **Bottom Footer Pill:** `Reviewed edits do not ensure full assignment coverage`.
  - **Review Status:** **Owner review pending** (Preserved under `image-candidates/`; not integrated into page bundle).

---

### 5. Concept Map Conditions: Illustrative Assumption on Connection

- **Page Bundle:** `content/blog/concept_map_conditions/index.md` (lines 20)
- **Candidate Path:** `docs/editorial/image-candidates/concept_map_conditions/candidate-01.png`
- **Tool / Method:** Antigravity `generate_image` (subscription native)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 620,085 bytes
- **SHA-256 Digest:** `37a74594052775cbc1614a897d1a539fae9250320fa6a2e54d583111b9a2c5c1`
- **Proposed Caption:** "The assumption belongs on the connection."
- **Proposed Alt Text:** "A proposed connection from partial order to total order states that every pair must be comparable and includes a source-reference symbol."
- **Exact Generation Prompt:**
  ```text
  A clean modern technical editorial illustration on a solid dark navy background (#14202D) with vibrant teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal diagram of an illustrative concept graph connection. Two spacious dark slate concept cards sit on opposite sides: left card titled 'Partial order' with subtext 'Reflexive, transitive, antisymmetric'; right card titled 'Total order' with subtext 'Partial order with full comparability'. A prominent horizontal arrow connects Partial order to Total order. Directly attached to the arrow is a clear condition label 'Every pair can be compared', a small citation badge 'Source: Section 1.2, p. 14', and a distinct status tag 'Proposed'. Clean flat vector graphic, crisp legible typography, generous spacing, illustrative diagram (not a software screenshot).
  ```
- **Visual & Factual Checks:**
  - **Core Concept:** Illustrates the requirement that graph edges carry explicit mathematical conditions and source anchors, using the sample relationship between partial orders and total orders.
  - **Spacious Concept Cards:** Left card titled "Partial order" (with mathematical properties: `Reflexive, transitive, antisymmetric`); right card titled "Total order" (`Partial order with full comparability`).
  - **Connection:** A clean directional teal arrow points from Partial order to Total order.
  - **Attached Details:** Attached directly to the arrow is the condition label box: `Every pair can be compared`. Below it are two distinct pills: citation badge `Source: Section 1.2, p. 14` and violet status tag `Proposed`.
  - **Negative Constraint Check:** Completely avoids depicting a dense software interface or fake full-course network screenshot; presents the sample relation cleanly as an editorial graphic.
  - **Review Status:** **Owner review pending** (Preserved under `image-candidates/`; not integrated into page bundle).

---

## Workspace & Git Verification

1. **Worktree Isolation:** Work executed strictly in `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-milestone-blog-images` on branch `gemini/milestone-blog-images`.
2. **Page Bundles Unchanged:**
   - All five blog draft files under `content/blog/<slug>/index.md` remain unmodified (`draft: true`, `[[Insert Image: ...]]` briefs intact).
   - No `featured.png` or `featured.jpg` files were added to the page bundles.
3. **Explicit Staging:**
   - Candidate assets and this report are staged explicitly:
     - `docs/editorial/image-candidates/practice_problem_checks/candidate-01.png`
     - `docs/editorial/image-candidates/resume_parser_milestone/candidate-01.png`
     - `docs/editorial/image-candidates/questions_in_lecture_notes/candidate-01.png`
     - `docs/editorial/image-candidates/reviewable_study_guides/candidate-01.png`
     - `docs/editorial/image-candidates/concept_map_conditions/candidate-01.png`
     - `docs/editorial/milestone-blog-image-report.md`
4. **No Merging / Pushing:**
   - No branches were merged, pushed, or deployed. All changes remain committed locally on `gemini/milestone-blog-images` awaiting owner review.
