# Gemini / Antigravity Image Generation Pilot Report

**Date:** 2026-10-18  
**Branch:** `gemini/website-images`  
**Repository Worktree:** `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-website-images`  
**Status:** **Pilot (3 images) + Batch 2 (5 images) integrated and committed; Batch 3 originals preserved; all 5 Batch 3 candidates + Source Indexer v2 generated and awaiting owner review**  

This report documents the three initial pilot image candidates created, revised, and integrated for Aaron Scherf's personal academic portfolio website, following the requirements and style guidance defined in [`docs/editorial/gemini-image-generation-handoff.md`](gemini-image-generation-handoff.md) and [`docs/editorial/gemini-image-generation-queue.md`](gemini-image-generation-queue.md).

All generated candidates use Antigravity's native image-generation capability under the owner's subscription, without invoking metered or paid third-party APIs. Per explicit owner decisions:
1. **Concept Graph:** Candidate 01 was declined as too simple; Candidate 02 (owner-supplied screenshot of the live web viewer) was approved and integrated as `featured.png`.
2. **Source Indexer:** Candidate 01 was approved and integrated as `featured.png`.
3. **Notes Transcription:** Candidate 01 was revised to Candidate 02 to visually embed the vector domain $\mathbb{R}^n$ directly into the slide and margin notes with a preserved math formatting callout. Caption explicitly labelled as an illustration. Candidate 02 was approved and integrated as `featured.png`.

---

## Pilot Candidate Summary Table

| Pilot | Page | Original Brief | Candidate Path | Dimensions | Tool / Model | Status |
|---|---|---|---|---|---|---|
| **1. Concept Graph (Candidate 01)** | [`content/projects/academic-hub/concept_graph/index.md`](../../content/projects/academic-hub/concept_graph/index.md) | `concept_graph/index.md` (L71); Queue row 28 | [`docs/editorial/image-candidates/concept_graph/candidate-01.png`](image-candidates/concept_graph/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Declined by owner** (too simple) |
| **1. Concept Graph (Candidate 02 / Integrated)** | [`content/projects/academic-hub/concept_graph/index.md`](../../content/projects/academic-hub/concept_graph/index.md) | Owner instruction: live site screenshot | [`docs/editorial/image-candidates/concept_graph/candidate-02.png`](image-candidates/concept_graph/candidate-02.png) | 1024 x 547 | User-uploaded screenshot | **Approved by owner & integrated** (`featured.png`) |
| **2. Source Indexer (Candidate 01 / Integrated)** | [`content/projects/academic-hub/source_indexer/index.md`](../../content/projects/academic-hub/source_indexer/index.md) | `source_indexer/index.md` (L59); Queue row 05 | [`docs/editorial/image-candidates/source_indexer/candidate-01.png`](image-candidates/source_indexer/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Approved by owner & integrated** (`featured.png`) |
| **3. Notes Transcription (Candidate 01)** | [`content/projects/academic-hub/notes_transcription/index.md`](../../content/projects/academic-hub/notes_transcription/index.md) | `notes_transcription/index.md` (L43); Queue row 01 | [`docs/editorial/image-candidates/notes_transcription/candidate-01.png`](image-candidates/notes_transcription/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Declined by owner** (text-only inset) |
| **3. Notes Transcription (Candidate 02 / Integrated)** | [`content/projects/academic-hub/notes_transcription/index.md`](../../content/projects/academic-hub/notes_transcription/index.md) | Owner revision: visual $\mathbb{R}^n$ integration | [`docs/editorial/image-candidates/notes_transcription/candidate-02.png`](image-candidates/notes_transcription/candidate-02.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Approved by owner & integrated** (`featured.png`) |

---

## Detailed Pilot Reviews

### 1. Concept Graph

#### Candidate 01 (Generated Illustration)
- **Output File Path:** `docs/editorial/image-candidates/concept_graph/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **Prompt:** Clean modern editorial diagram on dark navy background (#14202D)... Partial order to Total order with condition "Every pair can be compared".
- **Owner Review Decision:** **Declined** — owner feedback: *"The concept graph image is a little bit too simple, it doesn't really add much value. A simple screenshot of the site might be the best in this case."*

#### Candidate 02 (Owner-Supplied Screenshot — Integrated)
- **Output File Path:** `docs/editorial/image-candidates/concept_graph/candidate-02.png`
- **Page Bundle Asset:** `content/projects/academic-hub/concept_graph/featured.png`
- **Source:** User-uploaded live web screenshot (`https://aaronscherf.github.io/microecon-concept-graph/`)
- **Actual Dimensions:** 1024 x 547 pixels
- **File Size:** 435 KB
- **Integrated Caption:** "Screenshot of the interactive Microeconomics concept graph interface, showing concept nodes, connections, and the details panel for a selected concept."
- **Integrated Alt Text:** "Screenshot of the interactive Microeconomics concept graph web viewer showing interconnected nodes and the details panel for Rational preference relation."
- **Visual & Factual Inspection:**
  - Real, authentic screenshot of the live interactive web viewer.
  - Shows top bar with "Microeconomics concept graph" and review controls; left control sidebar with layouts and section filters; full graph canvas with interconnected nodes; right inspector panel with full metadata (summary, explanation, formal statement, and literature sources) for the selected "Rational preference relation" concept.
  - Crisp text legibility, authentic dark interface matching website aesthetic.
- **Integration Status:** **Completed** — saved to `content/projects/academic-hub/concept_graph/featured.png`, `image` metadata added to `index.md` frontmatter, and fulfilled `[[Insert Image: ...]]` block removed.

---

### 2. Source Indexer: Find a Passage, Not Just a File

#### Candidate 01 (Integrated)
- **Page:** `content/projects/academic-hub/source_indexer/index.md`
- **Original Brief Path:** `content/projects/academic-hub/source_indexer/index.md` (line 59); `docs/editorial/gemini-image-generation-queue.md` (Row 05)
- **Output File Path:** `docs/editorial/image-candidates/source_indexer/candidate-01.png`
- **Page Bundle Asset:** `content/projects/academic-hub/source_indexer/featured.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen capability under owner subscription)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 574 KB
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right: on the left, a small neat query box with text 'Where do my notes explain eigenvalues?'. A crisp arrow leads to a clean white card labelled 'Course'. Another arrow leads to two layered white cards labelled 'Document'. A third arrow leads to an enlarged white card labelled 'Passage'. Inside the Passage card, there is a highlighted box with simple clean text 'Av = λv defines eigenvalues of matrix A.' and an attached teal label badge reading 'p. 42'. Three prominent sans-serif labels: 'Course', 'Document', 'Passage'. Perfectly legible sans-serif typography, generous 8% outer margins, balanced 16:9 composition, flat clean aesthetic.
  ```
- **Integrated Caption:** "Illustration: find the document, then the passage worth reading."
- **Integrated Alt Text:** "An illustrative question narrows from course records to documents and a source-referenced passage."
- **Visual & Factual Inspection:**
  - **Composition & Subject:** Horizontal left-to-right hierarchy showing the narrowing progression: an illustrative query box ("Where do my notes explain eigenvalues?"), a "Course" card, two layered "Document" cards, and an enlarged "Passage" card.
  - **Labels & Progression:** Three large stage labels: "Course", "Document", and "Passage". The initial query cue reads exactly "Where do my notes explain eigenvalues?".
  - **Passage & Reference:** The passage card contains a highlighted genuine mathematical definition ("Av = λv defines eigenvalues of matrix A.") with an attached clean teal reference badge reading "p. 42".
  - **Spelling & Typography:** 100% correct spelling across all labels and mathematical text. No garbled text or pseudo-words.
  - **Constraints:** Avoids depicting a full search application, operating system chrome, or claiming that the illustration is a measured search retrieval result.
  - **Palette & Legibility:** Solid dark navy background (`#14202D`), crisp white cards with teal and violet accents. Broad margins (>8%) ensure thumbnail and mobile readability.
  - **Defects:** None observed.
- **Integration Status:** **Completed** — saved to `content/projects/academic-hub/source_indexer/featured.png`, older `featured.jpg` removed to avoid competing assets, `image` frontmatter updated, and fulfilled `[[Insert Image: ...]]` block removed.

---

### 3. Notes Transcription: Preserve Different Kinds of Information

#### Candidate 01 (Initial Inset Approach)
- **Output File Path:** `docs/editorial/image-candidates/notes_transcription/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **Owner Review Decision:** **Declined** — owner feedback: *"there is just a little box explaining the R^2 vs R2 issue, but it's just text, it doesn't really add anything visually. Could you adjust the example slide to include something about the domain of the vectors being R^n or something, then the handwritten repeats the R^n in handwritten form, and the transcription captures it correctly, with a little note under stating that the math formatting was preserved?"*

#### Candidate 02 (Integrated)
- **Page:** `content/projects/academic-hub/notes_transcription/index.md`
- **Original Brief Path:** `content/projects/academic-hub/notes_transcription/index.md` (line 43); `docs/editorial/gemini-image-generation-queue.md` (Row 01)
- **Output File Path:** `docs/editorial/image-candidates/notes_transcription/candidate-02.png`
- **Page Bundle Asset:** `content/projects/academic-hub/notes_transcription/featured.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen capability under owner subscription)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 692 KB
- **Exact Prompt:**
  ```text
  Clean modern technical editorial illustration on a solid dark navy background (#14202D). High contrast, minimalist graphic diagram with teal (#35C9C8) and muted violet (#A58AE0) accents. On the left side: a clean white presentation slide card titled 'Linear Maps' with printed text 'T: Rⁿ → Rᵐ where v ∈ Rⁿ'. In the slide's right margin is a visibly distinct casual handwritten note 'Domain in Rⁿ?'. Clean branching arrows lead to two transcription boxes on the right: the top box has a teal badge 'Slide' containing 'T: Rⁿ → Rᵐ where v ∈ Rⁿ' and a document icon; the bottom box has a violet badge 'Handwritten' containing 'Domain in Rⁿ?' and a document icon. Directly beneath the transcription boxes is a neat badge callout with text 'Math formatting preserved: Rⁿ superscript intact'. Minimalist, balanced 16:9 composition, crisp typography, generous margins, clean flat vector design.
  ```
- **Integrated Caption:** "Illustration: keep the handwriting, slide text, and source trail distinct while preserving mathematical superscripts."
- **Integrated Alt Text:** "A presentation slide and handwritten note with vector domain R^n are transcribed into distinct labelled blocks, with mathematical formatting and superscripts preserved."
- **Visual & Factual Inspection:**
  - **Slide & Notation:** Left card depicts a printed slide titled "Linear Maps" defining $T: \mathbb{R}^n \to \mathbb{R}^m$ where $\mathbf{v} \in \mathbb{R}^n$. In the right margin is an organic, cursive handwritten question: "Domain in $\mathbb{R}^n$?".
  - **Separation & Transcription:** Two clean transcription boxes on the right: "Slide" (teal badge with document marker) holding "$T: \mathbb{R}^n \to \mathbb{R}^m$ where $\mathbf{v} \in \mathbb{R}^n$", and "Handwritten" (violet badge with document marker) holding "Domain in $\mathbb{R}^n$?".
  - **Visual Callout:** Directly beneath the transcription regions, an attached callout tag reads: "Math formatting preserved: $\mathbb{R}^n$ superscript intact".
  - **Spelling & Typography:** 100% correct spelling across all labels, mathematical terms, and handwritten text. No corrupted words or extraneous boxes.
  - **Constraints:** Visually integrates the exponent challenge directly into the core math example rather than a detached text box. Maintains distinct handwritten vs. typed visual weight.
  - **Palette & Legibility:** Solid dark navy background (`#14202D`), teal `#35C9C8` and violet `#A58AE0` badges and borders, clean white cards. Generous margins (>8%).
  - **Defects:** None observed.
- **Integration Status:** **Completed** — saved to `content/projects/academic-hub/notes_transcription/featured.png`, older `featured.jpg` removed to avoid competing assets, `image` frontmatter updated with "Illustration:" prefix, and fulfilled `[[Insert Image: ...]]` block removed.

---

## Production Build and Visual Verification (Desktop & Mobile 390px)

In accordance with [`docs/editorial/gemini-image-generation-handoff.md`](gemini-image-generation-handoff.md), full production build and visual checks were performed and recorded for all three integrated pages.

### 1. Production Build Output
- **Command:** `hugo --minify`
- **Hugo Version:** v0.163.3 extended windows/amd64
- **Build Duration:** 3,740 ms
- **Statistics:**
  - Pages: 119
  - Paginator pages: 4
  - Non-page files: 32
  - Processed images: 523
  - Errors: 0
  - Warnings: 0

### 2. Article View Verification (Desktop & Mobile 390px)

| Page | Responsive Srcset Generated | Sizes Attribute | Rendered Caption | Rendered Article Alt Text | 390px Mobile & Desktop Legibility | Intended Claim Communicated |
|---|---|---|---|---|---|---|
| **Concept Graph** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Screenshot of the interactive Microeconomics concept graph interface, showing concept nodes, connections, and the details panel for a selected concept.</span>` | `alt="Screenshot of the interactive Microeconomics concept graph web viewer showing interconnected nodes and the details panel for Rational preference relation."` | Preserves 1024x547 aspect ratio without distortion; responsive downscaling to 390px maintains full interface structure and dark background harmony. | Authentically conveys live application interface scale and inspector detail. |
| **Source Indexer** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: find the document, then the passage worth reading.</span>` | `alt="An illustrative question narrows from course records to documents and a source-referenced passage."` | Bold stage labels ("Course", "Document", "Passage") and "p. 42" tag remain distinct and legible at 390px mobile viewport width. | Clear horizontal progression from question query to referenced passage. |
| **Notes Transcription** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: keep the handwriting, slide text, and source trail distinct while preserving mathematical superscripts.</span>` | `alt="A presentation slide and handwritten note with vector domain R^n are transcribed into distinct labelled blocks, with mathematical formatting and superscripts preserved."` | High-contrast white cards, teal/violet badges, distinct handwriting, and math preservation callout remain legible on 390px screens. | Distinct separation of typed vs. handwritten sources with mathematical exponents preserved. |

### 3. Collection Card / Thumbnail Verification (Desktop & Mobile 390px)

- **Listing Location:** `public/projects/academic-hub/index.html` (Academic Hub Collection)
- **Card Container Geometry:** `relative overflow-hidden aspect-[16/9] bg-gradient-to-br from-zinc-100 to-zinc-200 dark:from-zinc-800 dark:to-zinc-900`
- **Image Behavior:** `w-full h-full transition-transform duration-500 ease-out group-hover:scale-105 object-contain`
- **Responsive Srcset for Cards:** WebP variants at 400w, 600w, 800w with `sizes="(max-width: 768px) 100vw, (max-width: 1200px) 50vw, 33vw"`
- **Theme Alt Text Behavior:** Verified that HugoBlox collection cards utilize title-derived alt tags (`alt="Concept Graph featured image"`, `alt="Source Indexer featured image"`, `alt="Notes Transcription Pipeline featured image"`), matching documented theme behavior.
- **300px - 390px Thumbnail Crop Test:** Because `object-contain` is enforced within an exact 16:9 container, all three images display without focal-point clipping, awkward letterboxing, or distortion.

---

## Batch 2 Candidates Summary Table

| Item | Page | Original Brief | Candidate Path | Dimensions | Tool / Model | Status |
|---|---|---|---|---|---|---|
| **4. Study Guide Pipeline** | [`content/projects/academic-hub/study_guide_pipeline/index.md`](../../content/projects/academic-hub/study_guide_pipeline/index.md) | `study_guide_pipeline/index.md` (L70); Queue row 04 | [`docs/editorial/image-candidates/study_guide_pipeline/candidate-01.png`](image-candidates/study_guide_pipeline/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Approved by owner & integrated** (`featured.png`) |
| **5. Summary Enhancement** | [`content/projects/academic-hub/summary_enhancement/index.md`](../../content/projects/academic-hub/summary_enhancement/index.md) | `summary_enhancement/index.md` (L42); Queue row 06 | [`docs/editorial/image-candidates/summary_enhancement/candidate-01.png`](image-candidates/summary_enhancement/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Approved by owner & integrated** (`featured.png`) |
| **6. Guided Solutions** | [`content/projects/academic-hub/guided_solutions/index.md`](../../content/projects/academic-hub/guided_solutions/index.md) | `guided_solutions/index.md` (L36); Queue row 07 | [`docs/editorial/image-candidates/guided_solutions/candidate-01.png`](image-candidates/guided_solutions/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Approved by owner & integrated** (`featured.png`) |
| **7. Socratic Tutor** | [`content/projects/academic-hub/socratic_tutor/index.md`](../../content/projects/academic-hub/socratic_tutor/index.md) | `socratic_tutor/index.md` (L42); Queue row 08 | [`docs/editorial/image-candidates/socratic_tutor/candidate-01.png`](image-candidates/socratic_tutor/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Approved by owner & integrated** (`featured.png`) |
| **8. Corpus Health** | [`content/projects/academic-hub/corpus_health/index.md`](../../content/projects/academic-hub/corpus_health/index.md) | `corpus_health/index.md` (L57); Queue row 09 | [`docs/editorial/image-candidates/corpus_health/candidate-01.png`](image-candidates/corpus_health/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (Imagen) | **Approved by owner & integrated** (`featured.png`) |

---

## Detailed Batch 2 Candidate Reviews

### 4. Study Guide Pipeline: Human Review of Proposed Edits

- **Page:** `content/projects/academic-hub/study_guide_pipeline/index.md`
- **Original Brief Path:** `content/projects/academic-hub/study_guide_pipeline/index.md` (line 70); `docs/editorial/gemini-image-generation-queue.md` (Row 04)
- **Output File Path:** `docs/editorial/image-candidates/study_guide_pipeline/candidate-01.png`
- **Page Bundle Asset:** `content/projects/academic-hub/study_guide_pipeline/featured.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen capability under owner subscription)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 600 KB
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right with four distinct large stage labels: 'Choose sources', 'Draft guide', 'Review edits', and 'Revised guide'. Under 'Choose sources': two clean cards labelled 'Textbook' and 'Lecture notes'. Under 'Draft guide': a document titled 'Draft Guide' with text 'Wald Test'. Under 'Review edits': a human review card titled 'Human Review' with two clear proposal tags: a teal tag 'Add derivation Accepted' and a violet tag 'Drop citation Rejected'. Under 'Revised guide': a clean document titled 'Revised Guide' with text 'Newly added derivation' and a small overlapping card titled 'Original draft' kept beside it. Generous 8% outer margins, balanced 16:9 composition, crisp sans-serif typography, clean flat vector design.
  ```
- **Integrated Caption:** "Illustration: choose the materials, then decide which revisions to apply."
- **Integrated Alt Text:** "Selected sources become a draft; a person accepts or rejects proposed edits before a revised copy is created."
- **Visual & Factual Inspection:**
  - **Composition & Stages:** Four distinct horizontal stages matching the exact workflow requested: "Choose sources" → "Draft guide" → "Review edits" → "Revised guide".
  - **Review Point Focus:** The third stage, "Human Review", clearly showcases decision-making: "Add derivation" is marked with a teal "Accepted" pill, and "Drop citation" is marked with a violet "Rejected" pill.
  - **Preservation of Original Draft:** The final stage displays "Revised Guide" ("Newly added derivation") with the "Original draft" card retained directly alongside it to demonstrate that applying decisions produces a separate revised output.
  - **Typography & Spelling:** 100% correct typography; all stage headers and card labels are crisp and correctly spelled.
  - **Palette & Legibility:** Solid dark navy background (`#14202D`) with teal and muted violet accents; large fonts ensure readability at thumbnail and mobile viewports.
- **Integration Status:** **Completed** — saved to `content/projects/academic-hub/study_guide_pipeline/featured.png`, `image` metadata added to `index.md` frontmatter, and fulfilled `[[Insert Image: ...]]` block removed.

---

### 5. Summary Enhancement: Expand Reasoning While Keeping Source Trail

- **Page:** `content/projects/academic-hub/summary_enhancement/index.md`
- **Original Brief Path:** `content/projects/academic-hub/summary_enhancement/index.md` (line 42); `docs/editorial/gemini-image-generation-queue.md` (Row 06)
- **Output File Path:** `docs/editorial/image-candidates/summary_enhancement/candidate-01.png`
- **Page Bundle Asset:** `content/projects/academic-hub/summary_enhancement/featured.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen capability under owner subscription)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 695 KB
- **Exact Prompt:**
  ```text
  Clean modern technical editorial illustration on a solid dark navy background (#14202D). High contrast, minimalist graphic diagram with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal progression from left to right: On the left, a card titled 'Summary' showing the short formula 'OLS: β = (XᵀX)⁻¹Xᵀy'. In the middle, two source cards titled 'Textbook p. 112' and 'Lecture Note 4'. Clean curved connector lines branch from the sources to three distinct cards on the right: Card 1 labelled 'Assumptions' showing 'E[ε|X] = 0'; Card 2 labelled 'Derivation' showing 'Normal Equations: Xᵀ(y - Xβ) = 0'; Card 3 labelled 'Worked example' showing 'β̂ = 2.45' with a small neat calculator icon beside it. Balanced 16:9 composition, generous 8% outer margins, crisp typography, flat clean vector aesthetic.
  ```
- **Integrated Caption:** "Illustration: expand the reasoning while keeping the source trail."
- **Integrated Alt Text:** "A short summary and its source passages lead to a fuller explanation with assumptions, a derivation, and a computed example."
- **Visual & Factual Inspection:**
  - **Structure & Progression:** Left-to-right transformation showing a compact "Summary" card ($OLS: \beta = (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{y}$) connected via intermediate source cards ("Textbook p. 112" and "Lecture Note 4") to an expanded three-part breakdown.
  - **Three Expanded Sections:** The right side clearly displays three distinct cards: "Assumptions" ($\mathrm{E}[\epsilon|\mathbf{X}] = 0$), "Derivation" ($\mathbf{X}^T(\mathbf{y} - \mathbf{X}\beta) = 0$), and "Worked example" ($\hat{\beta} = 2.45$ with calculator icon).
  - **Mathematical Veracity:** Correct matrix OLS normal equations and conditional expectation notation; cleanly avoids cluttered or unreadable equations.
  - **Typography & Legibility:** Bold headers and clean monospace/serif math rendering; ample spacing prevents crowding.
- **Integration Status:** **Completed** — saved to `content/projects/academic-hub/summary_enhancement/featured.png`, `image` metadata added to `index.md` frontmatter, and fulfilled `[[Insert Image: ...]]` block removed.

---

### 6. Guided Solutions: Visible Authorship and Multi-Perspective Solutions

- **Page:** `content/projects/academic-hub/guided_solutions/index.md`
- **Original Brief Path:** `content/projects/academic-hub/guided_solutions/index.md` (line 36); `docs/editorial/gemini-image-generation-queue.md` (Row 07)
- **Output File Path:** `docs/editorial/image-candidates/guided_solutions/candidate-01.png`
- **Page Bundle Asset:** `content/projects/academic-hub/guided_solutions/featured.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen capability under owner subscription)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 646 KB
- **Exact Prompt:**
  ```text
  Clean modern technical editorial illustration on a solid dark navy background (#14202D). High contrast, minimalist graphic diagram with teal (#35C9C8) and muted violet (#A58AE0) accents. Balanced 16:9 composition. At the top, a clean banner card: 'Problem: Prove that the intersection of two open sets U and V is open'. Below it, three distinct equal-width cards side by side: 1. Left card titled 'My reasoning' with a casual handwritten thought bubble containing 'Point x must have a small radius fitting inside both sets'; 2. Middle card titled 'AI derivation' with teal top bar containing step-by-step mathematical proof: 'Let x ∈ U ∩ V. ∃ r₁, r₂ > 0 with B(x, r₁) ⊆ U, B(x, r₂) ⊆ V. Set r = min(r₁, r₂)'; 3. Right card titled 'After tutoring' with violet top bar containing a shorter proof path: 'Focus on key step: r = min(r₁, r₂) > 0 proves B(x, r) ⊆ U ∩ V'. Perfectly legible sans-serif typography, generous margins, clean flat vector design.
  ```
- **Integrated Caption:** "Illustration: three contributions to a solution, with their authorship kept visible."
- **Integrated Alt Text:** "A problem-set question with separate spaces for student reasoning, an AI derivation, and a proof developed through tutoring."
- **Visual & Factual Inspection:**
  - **Problem Header:** A top card frames the authentic mathematical question: "Problem: Prove that the intersection of two open sets U and V is open".
  - **Three Authorship Roles:** Three side-by-side cards clearly demarcate perspective:
    1. "My reasoning": Depicts an organic thought bubble with informal student intuition ("Point x must have a small radius fitting inside both sets").
    2. "AI derivation": Formal step-by-step topological proof with open balls $B(x, r_1) \subseteq U$ and $B(x, r_2) \subseteq V$, setting $r = \min(r_1, r_2)$.
    3. "After tutoring": Compact proof highlight showing the essential insight ($r = \min(r_1, r_2) > 0$).
  - **Mathematical & Visual Integrity:** Real mathematical definitions and clean notation without hallucinated characters or pseudo-proofs.
  - **Contrast & Hierarchy:** Clear header badges with teal and violet accents against dark navy.
- **Integration Status:** **Completed** — saved to `content/projects/academic-hub/guided_solutions/featured.png`, `image` metadata added to `index.md` frontmatter, and fulfilled `[[Insert Image: ...]]` block removed.

---

### 7. Socratic Tutor: Reply Check Against Established Steps

- **Page:** `content/projects/academic-hub/socratic_tutor/index.md`
- **Original Brief Path:** `content/projects/academic-hub/socratic_tutor/index.md` (line 42); `docs/editorial/gemini-image-generation-queue.md` (Row 08)
- **Output File Path:** `docs/editorial/image-candidates/socratic_tutor/candidate-01.png`
- **Page Bundle Asset:** `content/projects/academic-hub/socratic_tutor/featured.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen capability under owner subscription)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 687 KB
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow with three prominent stage labels: 'Student\'s reasoning', 'Reply check', and 'Tutor\'s next question'. On the left: a card labelled 'Student\'s reasoning' containing handwritten-style note 'f(x) is continuous on [a,b], but why does it achieve a maximum?'. In the center: a card labelled 'Reply check' with a top connector labelled 'Established steps', showing a green checkmark 'Step 1: Continuity identified' and a locked violet tag 'Step 2: Extreme Value Theorem Held back'. On the right: a card labelled 'Tutor\'s next question' with text 'What property does the closed interval [a,b] have?'. At the bottom, a discreet violet badge: 'Current limit: explaining new material'. Balanced 16:9 composition, crisp typography, generous 8% outer margins.
  ```
- **Integrated Caption:** "Illustration: check the next reply against what the student has established."
- **Integrated Alt Text:** "A student's reasoning updates a record of established steps, which is used to check the tutor's next question before sending it."
- **Visual & Factual Inspection:**
  - **Three Primary Elements:** "Student's reasoning", "Reply check", and "Tutor's next question" displayed in a clean three-card horizontal workflow.
  - **Gatekeeping & Step Record:** The central "Reply check" card illustrates the core mechanism: a checkmark for "Step 1: Continuity identified", alongside a padlock icon holding back "Step 2: Extreme Value Theorem Held back".
  - **Socratic Interaction:** The tutor card offers a guided inquiry ("What property does the closed interval [a,b] have?") rather than revealing the unreached theorem.
  - **Factual Honesty / Limitation Badge:** A bottom badge prominently notes "Current limit: explaining new material", directly addressing the brief's constraint to avoid claiming the teaching limitation is resolved.
  - **Typography & Visual Quality:** High contrast, legible typography, balanced spacing.
- **Integration Status:** **Completed** — saved to `content/projects/academic-hub/socratic_tutor/featured.png`, `image` metadata added to `index.md` frontmatter, and fulfilled `[[Insert Image: ...]]` block removed.

---

### 8. Corpus Health: Discover, Review, Repair, and Re-audit

- **Page:** `content/projects/academic-hub/corpus_health/index.md`
- **Original Brief Path:** `content/projects/academic-hub/corpus_health/index.md` (line 57); `docs/editorial/gemini-image-generation-queue.md` (Row 09)
- **Output File Path:** `docs/editorial/image-candidates/corpus_health/candidate-01.png`
- **Page Bundle Asset:** `content/projects/academic-hub/corpus_health/featured.png`
- **Tool / Model:** Antigravity `generate_image` (Imagen capability under owner subscription)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 710 KB
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Four large horizontal stage labels from left to right: 'Gap found', 'Owner review', 'Repair one document', and 'Check result'. Under 'Gap found': document card with warning icon and text 'Alert: Missing search passage'. Under 'Owner review': document card with text 'Review' and violet button 'Accept repair'. Under 'Repair one document': card with text 'Action: Targeted rebuild: single document'. Under 'Check result': card with text 'Audit: Result: restored passages' and teal badge 'Verified current'. A clean arrow leads from Action back to Owner review labelled 'Changed source: review again'. Balanced 16:9 composition, generous 8% margins, crisp typography, flat clean aesthetic.
  ```
- **Integrated Caption:** "Illustration: discover a gap, choose a repair, and check the result."
- **Integrated Alt Text:** "A missing search passage is reported for review, repaired for one document, and checked afterward; a changed source returns for review."
- **Visual & Factual Inspection:**
  - **Four Pipeline Stages:** Clear horizontal cards corresponding to "Gap found", "Owner review", "Repair one document", and "Check result".
  - **Targeted Repair & Loop-back:** Emphasizes that repair scope is restricted to a single document ("Action: Targeted rebuild: single document"), followed by post-action verification ("Audit: Result: restored passages", "Verified current").
  - **Changed Source Handling:** Distinct bottom loop-back arrow reading "Changed source: review again" connects Action back to Owner review, accurately reflecting the requirement that altered source material requires re-review rather than blind automation.
  - **Spelling & Legibility:** Clean typography, zero garbled text or spurious artifacts.
- **Integration Status:** **Completed** — saved to `content/projects/academic-hub/corpus_health/featured.png`, `image` metadata added to `index.md` frontmatter, and fulfilled `[[Insert Image: ...]]` block removed.

---

## Batch 2 Production Build and Visual Verification (Desktop & Mobile 390px)

Full production build and responsive visual checks were performed and recorded for all five Batch 2 integrated pages.

### 1. Production Build Output
- **Command:** `hugo --minify`
- **Hugo Version:** v0.163.3 extended windows/amd64
- **Build Duration:** 6,853 ms
- **Statistics:**
  - Pages: 119
  - Paginator pages: 4
  - Non-page files: 37
  - Processed images: 603 (80 new responsive WebP variants generated)
  - Errors: 0
  - Warnings: 0

### 2. Article View Verification (Desktop & Mobile 390px)

| Page | Responsive Srcset Generated | Sizes Attribute | Rendered Caption | Rendered Article Alt Text | 390px Mobile & Desktop Legibility | Intended Claim Communicated |
|---|---|---|---|---|---|---|
| **Study Guide Pipeline** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: choose the materials, then decide which revisions to apply.</span>` | `alt="Selected sources become a draft; a person accepts or rejects proposed edits before a revised copy is created."` | Four bold stages and Accepted/Rejected proposal badges remain clearly distinguishable and readable on 390px mobile screens. | Human review point with accepted/rejected decisions creating a new output. |
| **Summary Enhancement** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: expand the reasoning while keeping the source trail.</span>` | `alt="A short summary and its source passages lead to a fuller explanation with assumptions, a derivation, and a computed example."` | High-contrast cards for Assumptions, Derivation, and Worked Example with calculator icon scale down cleanly at 390px without equation distortion. | Three-part expansion connected to explicit course source citations. |
| **Guided Solutions** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: three contributions to a solution, with their authorship kept visible.</span>` | `alt="A problem-set question with separate spaces for student reasoning, an AI derivation, and a proof developed through tutoring."` | Problem header and three distinct authorship cards (thought bubble, formal proof, compact highlight) remain legible and clearly demarcated at 390px. | Visible multi-perspective solution retaining student intuition alongside AI proof. |
| **Socratic Tutor** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: check the next reply against what the student has established.</span>` | `alt="A student's reasoning updates a record of established steps, which is used to check the tutor's next question before sending it."` | Step checkmark, held-back padlock tag, question card, and bottom limitation badge remain sharp and readable on mobile devices. | Gated reply check preventing unreached theorem leaks while noting teaching limits. |
| **Corpus Health** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: discover a gap, choose a repair, and check the result.</span>` | `alt="A missing search passage is reported for review, repaired for one document, and checked afterward; a changed source returns for review."` | Four large stage cards, single-document action label, and changed-source loop-back arrow maintain legibility without card collisions at 390px. | Discovery, human review, targeted single-document rebuild, and changed-source re-review. |

### 3. Collection Card / Thumbnail Verification (Desktop & Mobile 390px)

- **Listing Location:** `public/projects/academic-hub/index.html` and `public/projects/index.html`
- **Responsive Srcset for Cards:** Generated WebP variants at 400w, 600w, 800w with `sizes="(max-width: 768px) 100vw, (max-width: 1200px) 50vw, 33vw"` and `object-contain` within exact 16:9 containers.
- **Thumbnail Legibility:** The bold headers, generous outer margins (>8%), and dark navy backgrounds ensure all five cards present clearly without awkward cropping or illegible micro-text in 300px–390px card grids.

---

## Workspace Status and Changes Summary

- **Repository Root:** `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-website-images`
- **Branch:** `gemini/website-images`
- **Committed Local Work:**
  - Commit `ea6faef`: Pilot images integrated for Concept Graph, Source Indexer, Notes Transcription.
  - Commit `d87e78e`: Batch 2 images integrated for Study Guide Pipeline, Summary Enhancement, Guided Solutions, Socratic Tutor, Corpus Health.
  - Commit `8e5056d`: Cherry-pick of original archives for Source Indexer, Notes Transcription, and baseline provenance inventory.

---

## Batch 3: Pilot Correction & Next Page Candidates

Dated: 2026-10-18  
Commit context: `8e5056df4b06698565ec38e1ae35b26208d91b06` (Originals recovery commit)

### Pilot Correction: Source Indexer (Candidate 02)

- **Page:** `content/projects/academic-hub/source_indexer/index.md`
- **Correction Requirement:** Eigenvalue statement must include a nonzero vector condition: $Av = \lambda v$ with $v \neq 0$.
- **Output File Path:** `docs/editorial/image-candidates/source_indexer/candidate-02.png`
- **Active Integrated Image:** `content/projects/academic-hub/source_indexer/featured.png` (retained unmodified pending review)
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 573 KB (586,636 bytes)
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right: on the left, a small neat query box with text 'Where do my notes explain eigenvalues?'. A crisp arrow leads to a clean white card labelled 'Course'. Another arrow leads to two layered white cards labelled 'Document'. A third arrow leads to an enlarged white card labelled 'Passage'. Inside the Passage card, there is a highlighted box with simple clean text 'Av = λv (v ≠ 0) defines eigenvalues of matrix A.' and an attached teal label badge reading 'p. 42'. Three prominent sans-serif labels: 'Course', 'Document', 'Passage'. Perfectly legible sans-serif typography, generous 8% outer margins, balanced 16:9 composition, flat clean aesthetic.
  ```
- **Visual & Factual Inspection:**
  - **Composition:** Perfectly preserves the approved Candidate 01 composition and card hierarchy ("Course" → "Document" → "Passage").
  - **Mathematical Correction:** The highlighted passage definition now explicitly states: `Av = λv (v ≠ 0) defines eigenvalues of matrix A.` with attached teal badge `p. 42`.
  - **Typography & Symbols:** The Greek letter $\lambda$ and inequality sign $\neq$ are sharply rendered with no artifacts.
  - **Review Status:** **Owner review pending** (Not integrated into page bundle).

---

### Batch 3 Candidates Summary Table

| Item | Page | Original Brief | Candidate Path | Dimensions | Original Archive | Status |
|---|---|---|---|---|---|---|
| **Corr. Source Indexer** | [`content/projects/academic-hub/source_indexer/index.md`](../../content/projects/academic-hub/source_indexer/index.md) | Owner correction: $v \neq 0$ condition | [`docs/editorial/image-candidates/source_indexer/candidate-02.png`](image-candidates/source_indexer/candidate-02.png) | 1376 x 768 (16:9) | `original-featured.jpg` (SHA-256: `6f6f58b6...`) | **Owner review pending** |
| **9. Project Steering** | [`content/projects/academic-hub/project_steering/index.md`](../../content/projects/academic-hub/project_steering/index.md) | `project_steering/index.md` (L41); Queue row 03 | [`docs/editorial/image-candidates/project_steering/candidate-01.png`](image-candidates/project_steering/candidate-01.png) | 1376 x 768 (16:9) | None at baseline / HEAD | **Owner review pending** |
| **10. Marker PDF Conversion** | [`content/projects/academic-hub/marker_conversion/index.md`](../../content/projects/academic-hub/marker_conversion/index.md) | `marker_conversion/index.md` (L59); Queue row 02 | [`docs/editorial/image-candidates/marker_conversion/candidate-01.png`](image-candidates/marker_conversion/candidate-01.png) | 1376 x 768 (16:9) | `original-featured.jpg` (SHA-256: `c6c176e1...`) | **Owner review pending** |
| **11. Notes Post-Processing** | [`content/projects/academic-hub/postprocess_notes/index.md`](../../content/projects/academic-hub/postprocess_notes/index.md) | `postprocess_notes/index.md` (L44); Queue row 10 | [`docs/editorial/image-candidates/postprocess_notes/candidate-01.png`](image-candidates/postprocess_notes/candidate-01.png) | 1376 x 768 (16:9) | `original-featured.jpg` (SHA-256: `a5f9c895...`) | **Owner review pending** |
| **12. RAG Analysis** | [`content/projects/academic-hub/rag_analysis/index.md`](../../content/projects/academic-hub/rag_analysis/index.md) | `rag_analysis/index.md` (L50); Queue row 11 | [`docs/editorial/image-candidates/rag_analysis/candidate-01.png`](image-candidates/rag_analysis/candidate-01.png) | 1376 x 768 (16:9) | `original-featured.jpg` (SHA-256: `262f423c...`) | **Owner review pending** |
| **13. Problem Generation** | [`content/projects/academic-hub/problem_generation/index.md`](../../content/projects/academic-hub/problem_generation/index.md) | `problem_generation/index.md` (L42); Queue row 12 | [`docs/editorial/image-candidates/problem_generation/candidate-01.png`](image-candidates/problem_generation/candidate-01.png) | 1376 x 768 (16:9) | `original-featured.jpg` (SHA-256: `f2e675e5...`) | **Owner review pending** |

---

### Detailed Batch 3 Reviews

#### 9. Project Steering: Owner-Reviewed Shortlist

- **Page:** `content/projects/academic-hub/project_steering/index.md`
- **Original Brief Path:** `content/projects/academic-hub/project_steering/index.md` (line 41); `docs/editorial/gemini-image-generation-queue.md` (Row 03)
- **Output File Path:** `docs/editorial/image-candidates/project_steering/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 657 KB (673,136 bytes)
- **Original Asset:** No featured image at baseline or HEAD commit; correctly recorded in `docs/editorial/image-originals-inventory.md`.
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right with three large prominent stage labels: 'Proposed', 'Review', and 'Ready'. Under 'Proposed': a clean white card listing five tasks: 'Format exam notes', 'Corpus scan trial', a highlighted row with a violet badge 'Missing estimate', 'Re-index lecture notes', and 'Export summary'. A clean teal arrow leads to 'Review': a central card labelled 'Owner Review' with a violet badge 'Approval'. A curved purple arrow leads from Ready back to Review labelled 'Changed task: return to review'. A clean teal arrow leads to 'Ready': a clean white shortlist card titled 'Shortlist' showing three numbered tasks: '1. Re-index lecture notes', '2. Verify study guide', and '3. Export summary'. At the bottom center, a discreet pill tag: 'Prioritized, not implemented'. Minimalist flat vector aesthetic, crisp sans-serif typography, generous margins, balanced 16:9 composition.
  ```
- **Proposed Caption:** "A shortlist built from decisions I have reviewed."
- **Proposed Alt Text:** "Task suggestions pass through owner review; changed tasks and missing estimates stay out of the ready shortlist."
- **Visual & Factual Inspection:**
  - **Workflow & Stages:** Clear three-stage pipeline matching the brief: "Proposed" → "Review" → "Ready".
  - **Constraint Fulfillment:**
    - The "Proposed" card lists tasks, with one highlighted row held back by a violet "Missing estimate" badge.
    - A curved return arrow explicitly labelled "Changed task: return to review" links from the ready stage back to Owner Review.
    - The "Ready" card contains an explicit 3-item "Shortlist" of prioritized tasks.
    - Bottom pill explicitly communicates: "Prioritized, not implemented", reinforcing that priority decisions are separate from implementation.
  - **Legibility & Quality:** Crisp typography, solid dark navy background (`#14202D`), no stray characters or spelling errors.
- **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 10. Marker PDF Conversion: Structure, Figure Descriptions, and Page Tracking

- **Page:** `content/projects/academic-hub/marker_conversion/index.md`
- **Original Brief Path:** `content/projects/academic-hub/marker_conversion/index.md` (line 59); `docs/editorial/gemini-image-generation-queue.md` (Row 02)
- **Output File Path:** `docs/editorial/image-candidates/marker_conversion/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 790 KB (808,508 bytes)
- **Original Archive:** `docs/editorial/image-candidates/marker_conversion/original-featured.jpg` (SHA-256: `c6c176e17efa8650e14604dd685b1320d2d1110d88fa3f23ba89902f4161057c`, 631,466 bytes)
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal progression from left to right: On the left, an open textbook spread card titled 'Chapter 3: Spectral Theory' with two distinct page badges: teal badge 'PDF p. 165' and violet badge 'Printed p. 157', featuring a simple geometric diagram. Clean branching arrows lead to two structured output cards on the right: Top card titled 'Chapter Excerpt' with subheader '3.2 Normal Operators', cross-reference text 'Reference: printed p. 157', and a source anchor tag; Bottom card titled 'Figure Description' with text 'Fig 3.1: Orthogonal projection diagram' and a searchable text badge. Balanced 16:9 composition, generous outer padding, perfectly legible sans-serif typography, clean flat vector aesthetic.
  ```
- **Proposed Caption:** "Preserve the structure needed to find and check a passage."
- **Proposed Alt Text:** "A textbook chapter, equation, and figure become searchable text with both PDF and printed-page references."
- **Visual & Factual Inspection:**
  - **Structure & Dual Page Anchors:** Left card illustrates an open textbook spread titled "Chapter 3: Spectral Theory", clearly displaying both "PDF p. 165" (teal) and "Printed p. 157" (violet) badges.
  - **Branching Outputs:** Two structured right cards:
    1. "Chapter Excerpt": "3.2 Normal Operators", "Reference: printed p. 157", and "Source anchor tag" pill.
    2. "Figure Description": "Fig 3.1: Orthogonal projection diagram" with "Searchable text" badge.
  - **Graphic Illustration:** A clean 3D orthogonal projection diagram connects visually to the figure description card.
  - **Legibility & Quality:** Sharp typography, excellent contrast, perfectly legible at thumbnail width.
- **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 11. Notes Post-Processing: Symbol Verification Against Source

- **Page:** `content/projects/academic-hub/postprocess_notes/index.md`
- **Original Brief Path:** `content/projects/academic-hub/postprocess_notes/index.md` (line 44); `docs/editorial/gemini-image-generation-queue.md` (Row 10)
- **Output File Path:** `docs/editorial/image-candidates/postprocess_notes/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 740 KB (757,912 bytes)
- **Original Archive:** `docs/editorial/image-candidates/postprocess_notes/original-featured.jpg` (SHA-256: `a5f9c8954c44a0fa633f9f38a9053b4a5e727fb2754a1ed5e9dcdc83348d0372`, 700,834 bytes)
- **Exact Prompt:**
  ```text
  Clean modern technical editorial illustration on a solid dark navy background (#14202D). High contrast, minimalist graphic diagram with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal three-stage comparison from left to right: 1. Left card labelled 'Source Page' showing typeset mathematical formula with a clear radical symbol '√(h² + k²)'; 2. Middle card labelled 'Mistaken Extraction' showing formula 'p(h² + k²)' where the first letter 'p' is highlighted in a soft amber warning box with label 'Suspicious symbol'; A verification arrow connects from the source page to the correction; 3. Right card labelled 'Corrected Reading' showing '√(h² + k²)' with the radical symbol '√' highlighted in a teal badge with label 'Verified against source: p → √'. Discreet bottom note: 'Illustrative example, not automated proof'. Balanced 16:9 composition, generous outer margins, crisp typography, clean vector design.
  ```
- **Proposed Caption:** "One ordinary-looking letter can change the meaning of an equation."
- **Proposed Alt Text:** "The letter p in extracted text is replaced with a square-root sign after comparison with the source formula."
- **Visual & Factual Inspection:**
  - **Comparison Layout:** Three cards showing the exact progression requested:
    1. "Source Page": Clean formulas with genuine square root: $\gamma = \sqrt{h^2 + k^2}$, $h = \frac{\sqrt{h^2 + k^2}}{h + k}$.
    2. "Mistaken Extraction": $p(h^2 + k^2)$ with the first symbol $p$ enclosed in an amber "Suspicious symbol" box.
    3. "Corrected Reading": $\sqrt{h^2 + k^2}$ with the radical symbol $\sqrt{}$ highlighted in teal and tagged "Verified against source: $p \to \sqrt{}$".
  - **Bottom Tag:** "Illustrative example, not automated proof", directly addressing the constraint to avoid claiming complete equation verification.
  - **Defect Note:** The generator duplicated the stage headings above and below each card ("Source Page", "Mistaken Extraction", "Corrected Reading"). While all mathematical terms, callouts, and badges are crisp and readable, this minor duplicate heading is recorded for review.
- **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 12. RAG Analysis: Dual-Source Passage Grounding and Inspectable Route Back

- **Page:** `content/projects/academic-hub/rag_analysis/index.md`
- **Original Brief Path:** `content/projects/academic-hub/rag_analysis/index.md` (line 50); `docs/editorial/gemini-image-generation-queue.md` (Row 11)
- **Output File Path:** `docs/editorial/image-candidates/rag_analysis/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 704 KB (720,754 bytes)
- **Original Archive:** `docs/editorial/image-candidates/rag_analysis/original-featured.jpg` (SHA-256: `262f423c91066bf1a8cdc34de4d02919ba24425155cfcba24b6ee3ccd7a02693`, 596,934 bytes)
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right: On the left, a card labelled 'Question' with text 'What does the spectral theorem explain?'. Clean arrows branch to two central source passage cards: top card labelled 'Textbook Passage' with violet badge 'Sec 7.4, p. 264' and text 'Real eigenvalues with orthogonal eigenvectors'; bottom card labelled 'Lecture Notes' with teal badge 'Lecture 12, p. 3' and text 'Orthogonal directions act as pure scaling axes'. Connector arrows merge into an 'Answer' card on the right with concise explanation 'Perpendicular scaling directions simplify matrix analysis' and an attached inspectable reference tag 'Source trail: Sec 7.4, pp. 264–266'. Discreet bottom badge: 'Illustrative: reference enables inspection'. Balanced 16:9 composition, generous outer margins, crisp typography, flat clean vector aesthetic.
  ```
- **Proposed Caption:** "Keep an explanation connected to the passages used to write it."
- **Proposed Alt Text:** "Two source passages support an illustrative answer with a section and page reference that can be checked."
- **Visual & Factual Inspection:**
  - **Workflow & Structure:** Left-to-right progression from an illustrative question to two distinct source passages and a referenced answer.
  - **Dual Source Grounding:** Shows a "Textbook Passage" (Sec 7.4, p. 264: "Real eigenvalues with orthogonal eigenvectors") and "Lecture Notes" (Lecture 12, p. 3: "Orthogonal directions act as pure scaling axes").
  - **Inspectable Route Back:** The answer card features an attached "Source trail: Sec 7.4, pp. 264–266" tag, enabling inspection.
  - **Bottom Tag:** "Illustrative: reference enables inspection", explicitly clarifying that references guide inspection rather than guaranteeing flawless interpretation.
  - **Typography & Integrity:** Zero spelling or mathematical errors, high contrast, clean vector aesthetic.
- **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 13. Problem Generation: Separate Method and Correctness Checks

- **Page:** `content/projects/academic-hub/problem_generation/index.md`
- **Original Brief Path:** `content/projects/academic-hub/problem_generation/index.md` (line 42); `docs/editorial/gemini-image-generation-queue.md` (Row 12)
- **Output File Path:** `docs/editorial/image-candidates/problem_generation/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 621 KB (635,895 bytes)
- **Original Archive:** `docs/editorial/image-candidates/problem_generation/original-featured.jpg` (SHA-256: `f2e675e5a8173a3bae285b2251723d260382bbf227569dffb3af2e0e4ccca539`, 562,108 bytes)
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal progression from left to right: On the left, a card labelled 'Practice Request' with text 'Show 1/n → 0 using ε-N definition'. A crisp arrow leads to 'Draft Solution' card with text 'Choose N > 1/ε; then |1/n| < ε'. Clean arrows lead to two separate verification checks stacked vertically: top check with teal badge 'Requested method? PASS (ε-N applied)'; bottom check with violet badge 'Correct reasoning? PASS (inequalities valid)'. An arrow leads to the final stage: a clean card labelled 'Human Inspection' with a review checklist icon and note 'Student verifies reasoning'. Discreet bottom tag: 'Illustrative demonstration'. Balanced 16:9 composition, generous 8% outer margins, crisp sans-serif typography, clean flat vector design.
  ```
- **Proposed Caption:** "The right answer and the right method are separate checks."
- **Proposed Alt Text:** "A practice problem and solution are reviewed for both the requested technique and mathematical correctness before student inspection."
- **Visual & Factual Inspection:**
  - **Workflow & Structure:** Follows a progression from "Practice Request" to "Draft Solution", split into two independent verification checks, culminating in "Human Inspection".
  - **Two Independent Checks:**
    1. "Requested method? PASS (ε-N applied)" (teal badge)
    2. "Correct reasoning? PASS (inequalities valid)" (violet badge)
  - **Human Verification:** The final card explicitly requires "Human Inspection" ("Student verifies reasoning") with a checklist icon.
  - **Mathematical Integrity:** Correct sequence convergence formulation ($\forall \epsilon > 0, N > 1/\epsilon \implies |1/n| < \epsilon$).
  - **Bottom Tag:** "Illustrative demonstration".
  - **Typography & Integrity:** Zero spelling defects, clean vector styling.
- **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

## Batch 3 Candidate Revisions (Round 2 — 2026-10-19)

Targeted corrections requested by the owner for four Batch 3 candidates. All previous originals, candidate files, and approved featured images are preserved. No page bundles have been modified.

### Summary Table of Active Batch 3 Review Candidates

| Item | Page | Candidate Path | Dimensions | Status | Key Correction / Feature |
|---|---|---|---|---|---|
| **Corr. Source Indexer** | [`source_indexer`](../../content/projects/academic-hub/source_indexer/index.md) | [`candidate-02.png`](image-candidates/source_indexer/candidate-02.png) | 1376 x 768 (16:9) | **Owner review pending** (Unchanged from R1) | $\mathbf{Av} = \lambda \mathbf{v} \; (\mathbf{v} \neq 0)$ |
| **9. Project Steering** | [`project_steering`](../../content/projects/academic-hub/project_steering/index.md) | [`candidate-02.png`](image-candidates/project_steering/candidate-02.png) | 1376 x 768 (16:9) | **Owner review pending** (Revised R2) | Shortlist contains only proposed tasks; 'Format exam notes' replaces unproposed task; 'Corpus scan trial' missing estimate held back |
| **10. Marker Conversion** | [`marker_conversion`](../../content/projects/academic-hub/marker_conversion/index.md) | [`candidate-01.png`](image-candidates/marker_conversion/candidate-01.png) | 1376 x 768 (16:9) | **Owner review pending** (Unchanged from R1) | Dual PDF & printed page tracking, figure description |
| **11. Notes Post-Processing** | [`postprocess_notes`](../../content/projects/academic-hub/postprocess_notes/index.md) | [`candidate-02.png`](image-candidates/postprocess_notes/candidate-02.png) | 1376 x 768 (16:9) | **Owner review pending** (Revised R2) | Removed unrelated lower equation and duplicate bottom headers; focused strictly on single expression $\sqrt{h^2 + k^2}$ and $p \to \sqrt{}$ correction |
| **12. RAG Analysis** | [`rag_analysis`](../../content/projects/academic-hub/rag_analysis/index.md) | [`candidate-02.png`](image-candidates/rag_analysis/candidate-02.png) | 1376 x 768 (16:9) | **Owner review pending** (Revised R2) | Added explicit "real symmetric matrix" condition to question and textbook passage; inspectable source trail |
| **13. Problem Generation** | [`problem_generation`](../../content/projects/academic-hub/problem_generation/index.md) | [`candidate-02.png`](image-candidates/problem_generation/candidate-02.png) | 1376 x 768 (16:9) | **Owner review pending** (Revised R2) | Completed convergence proof ($\forall n \ge N, |1/n| \le 1/N < \varepsilon$); split method and reasoning checks with human inspection |

---

### Detailed Reviews of Revised Candidates

#### 9. Project Steering: Proposed-Task Alignment & Shortlist Derivation (Candidate 02)

- **Page:** `content/projects/academic-hub/project_steering/index.md`
- **Output File Path:** `docs/editorial/image-candidates/project_steering/candidate-02.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 654,708 bytes
- **SHA-256 Digest:** `8de74ce3a4dafbb62ce0cf403cad1a890c3c7cbd5fdbbe1ed17f5de3245a0541`
- **Proposed Caption:** "A shortlist built from decisions I have reviewed."
- **Proposed Alt Text:** "Task suggestions pass through owner review; changed tasks and missing estimates stay out of the ready shortlist."
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right with three large prominent stage labels: 'Proposed', 'Review', and 'Ready'. Under 'Proposed': a clean white card listing four tasks: 'Format exam notes', 'Corpus scan trial' with an attached violet badge 'Missing estimate', 'Re-index lecture notes', and 'Export summary'. A clean teal arrow leads to 'Review': a central card labelled 'Owner Review' with a violet badge 'Approval'. A curved purple arrow leads from Ready back to Review labelled 'Changed task: return to review'. A clean teal arrow leads to 'Ready': a clean white shortlist card titled 'Shortlist' containing three numbered tasks from the proposed list: '1. Re-index lecture notes', '2. Format exam notes', and '3. Export summary'. At the bottom center, a discreet pill tag: 'Prioritized, not implemented'. Minimalist flat vector aesthetic, crisp sans-serif typography, generous outer margins, balanced 16:9 composition.
  ```
- **Visual & Factual Inspection:**
  - **Proposed Task List:** Contains four clean tasks: "Format exam notes", "Corpus scan trial", "Re-index lecture notes", and "Export summary".
  - **Missing Estimate Hold-Back:** A violet badge reading "Missing estimate" is directly attached beneath "Corpus scan trial", visibly justifying why it does not advance to the ready shortlist.
  - **Shortlist Alignment:** The "Shortlist" on the Ready card consists exclusively of tasks originating in the Proposed list:
    1. "Re-index lecture notes"
    2. "Format exam notes" (replacing the unproposed "Verify study guide" from Candidate 01)
    3. "Export summary"
  - **Changed-Task Loop & State Distinction:** A curved purple connector arrow links from Ready back to Review: "Changed task: return to review". A bottom centered pill tag clearly states: "Prioritized, not implemented".
  - **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 11. Notes Post-Processing: Focused Expression & Clean Layout (Candidate 02)

- **Page:** `content/projects/academic-hub/postprocess_notes/index.md`
- **Output File Path:** `docs/editorial/image-candidates/postprocess_notes/candidate-02.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 652,232 bytes
- **SHA-256 Digest:** `579f6163ccbd60a27276b3156e3e06807df9e1a06e5170156708c4f73e212c63`
- **Proposed Caption:** "One ordinary-looking letter can change the meaning of an equation."
- **Proposed Alt Text:** "The letter p in extracted text is replaced with a square-root sign after comparison with the source formula."
- **Exact Prompt:**
  ```text
  Clean modern technical editorial illustration on a solid dark navy background (#14202D). High contrast, minimalist graphic diagram with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal three-stage comparison across three distinct white cards: 1. Left card with single top title 'Source Page' showing exactly one formula with a clean radical symbol '√(h² + k²)' and no other equations; 2. Middle card with single top title 'Mistaken Extraction' showing formula 'p(h² + k²)' where the initial letter 'p' is highlighted in an amber warning box labelled 'Suspicious symbol'; A verification connector arrow leads from the source page to the correction; 3. Right card with single top title 'Corrected Reading' showing '√(h² + k²)' with the radical sign '√' highlighted in a teal badge labelled 'Verified against source: p → √'. Only have titles at the top of each card; do not place any duplicate titles or labels below the cards. Discreet bottom note: 'Illustrative example, not automated proof'. Balanced 16:9 composition, generous outer margins, crisp typography, clean vector aesthetic.
  ```
- **Visual & Factual Inspection:**
  - **Single Focused Expression:** The unrelated lower equation from Candidate 01 has been removed; the Source Page card now displays solely the target expression: $\sqrt{h^2 + k^2}$.
  - **Removal of Duplicate Headings:** The redundant stage headings beneath the cards from Candidate 01 are eliminated. Only clean top titles appear ("Source Page", "Mistaken Extraction", "Corrected Reading").
  - **Three-Stage Progression:**
    1. Source Page: $\sqrt{h^2 + k^2}$
    2. Mistaken Extraction: $p(h^2 + k^2)$ with $p$ enclosed in amber badge "Suspicious symbol".
    3. Corrected Reading: $\sqrt{h^2 + k^2}$ with radical $\sqrt{}$ highlighted in teal and callout badge "Verified against source: $p \to \sqrt{}$".
  - **Verification Trail & Qualification:** A verification connector links the source to the correction, and the bottom note explicitly declares: "Illustrative example, not automated proof".
  - **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 12. RAG Analysis: Explicit Real Symmetric Matrix Condition (Candidate 02)

- **Page:** `content/projects/academic-hub/rag_analysis/index.md`
- **Output File Path:** `docs/editorial/image-candidates/rag_analysis/candidate-02.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 705,186 bytes
- **SHA-256 Digest:** `ecb8f43a733af97537cd3062d422d81b0a2b08cff46bebc06271d87371639fe4`
- **Proposed Caption:** "Keep an explanation connected to the passages used to write it."
- **Proposed Alt Text:** "Two source passages support an illustrative answer with a section and page reference that can be checked."
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right: On the left, a card labelled 'Question' with text 'How does the spectral theorem help with real symmetric matrices?'. Clean arrows branch to two central source passage cards: top card labelled 'Textbook Passage' with violet badge 'Sec 7.4, p. 264' and text 'A real symmetric matrix has an orthonormal eigenbasis.'; bottom card labelled 'Lecture Notes' with teal badge 'Lecture 12, p. 3' and text 'Each eigenvector direction is scaled by its eigenvalue.'. Connector arrows merge into an 'Answer' card on the right with concise explanation 'Orthogonal eigenvector coordinates turn the transformation into separate scaling operations.' and an attached inspectable reference tag 'Source trail: Sec 7.4, pp. 264–266'. Discreet bottom badge: 'Illustrative: reference enables inspection'. Balanced 16:9 composition, generous outer margins, crisp sans-serif typography, flat clean vector aesthetic.
  ```
- **Visual & Factual Inspection:**
  - **Mathematical Condition:** The question explicitly states: "How does the spectral theorem help with real symmetric matrices?", and the textbook passage specifies: "A real symmetric matrix has an orthonormal eigenbasis." (with violet badge "Sec 7.4, p. 264"). This ensures no false implication that arbitrary matrices have real eigenvalues or orthogonal eigenbases.
  - **Lecture Passage & Explanation:** Lecture notes card shows "Each eigenvector direction is scaled by its eigenvalue." (teal badge "Lecture 12, p. 3"). Answer states: "Orthogonal eigenvector coordinates turn the transformation into separate scaling operations."
  - **Inspectable Source Trail:** An attached tag records "Source trail: Sec 7.4, pp. 264–266".
  - **Discreet Qualification:** Bottom pill clearly reads "Illustrative: reference enables inspection".
  - **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 13. Problem Generation: Complete Convergence Argument (Candidate 02)

- **Page:** `content/projects/academic-hub/problem_generation/index.md`
- **Output File Path:** `docs/editorial/image-candidates/problem_generation/candidate-02.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 672,989 bytes
- **SHA-256 Digest:** `bc91d1a9799577446687ff7e807d0c455ac3c85da189010ddfdc203c70a2689f`
- **Proposed Caption:** "The right answer and the right method are separate checks."
- **Proposed Alt Text:** "A practice problem and solution are reviewed for both the requested technique and mathematical correctness before student inspection."
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal progression from left to right across clean white cards: 1. Left card labelled 'Practice Request' with text 'Show 1/n → 0 using ε-N definition'; 2. Crisp arrow leads to 'Draft Solution' card with complete proof: 'Given ε > 0, choose N ∈ ℕ with N > 1/ε. For every n ≥ N, |1/n| ≤ 1/N < ε.'; 3. Clean arrows lead to two separate verification checks stacked vertically: top check with teal badge 'Requested method? PASS (ε-N applied)'; bottom check with violet badge 'Correct reasoning? PASS (inequalities valid)'; 4. Arrow leads to final card labelled 'Human Inspection' with review checklist icon and note 'Student verifies reasoning'. Discreet bottom tag: 'Illustrative demonstration'. Balanced 16:9 composition, generous 8% outer margins, crisp sans-serif typography, flat clean vector design.
  ```
- **Visual & Factual Inspection:**
  - **Complete Mathematical Argument:** The Draft Solution card now contains the rigorous, complete convergence proof:
    $$\text{Given } \varepsilon > 0, \text{ choose } N \in \mathbb{N} \text{ with } N > \frac{1}{\varepsilon}.$$
    $$\text{For every } n \ge N, \left|\frac{1}{n}\right| \le \frac{1}{N} < \varepsilon.$$
    This explicitly establishes the inequality for all $n \ge N$, correcting the incomplete argument from Candidate 01.
  - **Independent Verification Checks:**
    1. "Requested method? PASS (ε-N applied)" (teal ribbon badge)
    2. "Correct reasoning? PASS (inequalities valid)" (violet ribbon badge)
  - **Human Inspection Stage:** Connects to final "Human Inspection" card with checklist and "Student verifies reasoning".
  - **Discreet Qualification:** Bottom pill tag clearly reads "Illustrative demonstration".
  - **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

## Batch 3 Production Build and Visual Verification (Desktop & Mobile 390px)

Full production build and responsive visual checks were performed and recorded for all six integrated pages (Source Indexer candidate 02, Project Steering candidate 02, Marker Conversion candidate 01, Notes Post-Processing candidate 02, RAG Analysis candidate 02, and Problem Generation candidate 02).

### 1. Production Build Output
- **Command:** `hugo --minify`
- **Hugo Version:** v0.163.3 extended windows/amd64
- **Build Duration:** 18,675 ms
- **Statistics:**
  - Pages: 119
  - Paginator pages: 4
  - Non-page files: 38
  - Processed images: 619 (new responsive WebP variants generated across all viewports)
  - Errors: 0
  - Warnings: 0

### 2. Article View Verification (Desktop & Mobile 390px)

| Page | Responsive Srcset Generated | Sizes Attribute | Rendered Caption | Rendered Article Alt Text | 390px Mobile & Desktop Legibility | Intended Claim Communicated |
|---|---|---|---|---|---|---|
| **Source Indexer** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: find the document, then the passage worth reading.</span>` | `alt="An illustrative question narrows from course records to documents and a source-referenced passage."` | Nonzero eigenvector condition $\mathbf{Av} = \lambda \mathbf{v} \; (\mathbf{v} \neq 0)$ and page 42 badge remain crisp and sharp at 390px mobile width. | Search narrowing from course to document to verified referenced passage. |
| **Project Steering** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: a shortlist built from decisions I have reviewed.</span>` | `alt="Task suggestions pass through owner review; changed tasks and missing estimates stay out of the ready shortlist."` | Proposed task list, missing estimate hold-back, and 3-item ready shortlist scale down cleanly with balanced spacing. | Owner review gate; unestimated tasks held back; changed tasks return to review. |
| **Marker Conversion** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: preserve the structure needed to find and check a passage.</span>` | `alt="A textbook chapter, equation, and figure become searchable text with both PDF and printed-page references."` | Dual PDF and printed page tracking badges and figure description card remain clearly legible at 390px. | Structural conversion preserving book references and geometric figure descriptions. |
| **Notes Post-Processing** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: one ordinary-looking letter can change the meaning of an equation.</span>` | `alt="The letter p in extracted text is replaced with a square-root sign after comparison with the source formula."` | Single formula focus $\sqrt{h^2 + k^2}$, amber suspicious symbol badge, and teal verification badge maintain high contrast and clarity. | Detection and source comparison of plausible optical extraction errors without claiming automated proof. |
| **RAG Analysis** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: keep an explanation connected to the passages used to write it.</span>` | `alt="Two source passages support an illustrative answer with a section and page reference that can be checked."` | Explicit real symmetric matrix condition, dual textbook/lecture citations, and source trail tag are legible without overlap at 390px. | Dual-source grounding with inspectable reference route back to source pages. |
| **Problem Generation** | 320w, 480w, 640w, 720w (WebP) | `(max-width: 480px) 100vw, (max-width: 640px) 90vw, (max-width: 720px) 80vw, 720px` | `<span class=article-header-caption>Illustration: the right answer and the right method are separate checks.</span>` | `alt="A practice problem and solution are reviewed for both the requested technique and mathematical correctness before student inspection."` | Complete convergence argument ($\forall n \ge N, |1/n| \le 1/N < \varepsilon$), stacked method/correctness check badges, and human inspection stage remain sharp on mobile. | Separate evaluation of method and reasoning validity culminating in human student inspection. |

### 3. Collection Card / Thumbnail Verification (Desktop & Mobile 390px)

- **Listing Location:** `public/projects/academic-hub/index.html` and `public/projects/index.html`
- **Responsive Srcset for Cards:** Generated WebP variants at 400w, 600w, 800w with `sizes="(max-width: 768px) 100vw, (max-width: 1200px) 50vw, 33vw"` and `object-contain` within exact 16:9 containers.
- **Thumbnail Legibility:** High contrast dark navy background (`#14202D`), generous outer padding (>8%), and bold card headers ensure all six project cards display cleanly without cropping or illegible micro-text in 300px–390px grid views.

---

## Batch 4 Candidates (Prepared for Owner Review — 2026-10-19)

Dated: 2026-10-19  
Originals preserved and hash-verified in `docs/editorial/image-originals-inventory.md`. All five candidates prepared under `docs/editorial/image-candidates/` awaiting owner review. No page bundles or articles have been modified for Batch 4.

### Batch 4 Candidates Summary Table

| Item | Page | Candidate Path | Dimensions | Tool / Generation Method | Status |
|---|---|---|---|---|---|
| **14. Journal Discovery** | [`journal_discovery`](../../content/projects/ai-research-assistant/journal_discovery/index.md) | [`candidate-01.png`](image-candidates/journal_discovery/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (`gemini-3.1-flash-image`) | **Owner review pending** |
| **15. Visualization** | [`visualization`](../../content/projects/academic-hub/visualization/index.md) | [`candidate-01.png`](image-candidates/visualization/candidate-01.png) | 1376 x 768 (16:9) | Rendered mathematical plot (`agent/viz/templates/gradient_descent.py`) | **Owner review pending** |
| **16. Resume Manager** | [`resume_manager`](../../content/projects/resume_manager/index.md) | [`candidate-02.png`](image-candidates/resume_manager/candidate-02.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (`gemini-3.1-flash-image`) | **Owner review pending** (Revised to gear icon) |
| **17. Video Lecture Notes** | [`video_notes`](../../content/projects/academic-hub/video_notes/index.md) | [`candidate-01.png`](image-candidates/video_notes/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (`gemini-3.1-flash-image`) | **Owner review pending** |
| **18. Tutor Diagnosis** | [`tutor_diagnosis`](../../content/projects/academic-hub/tutor_diagnosis/index.md) | [`candidate-01.png`](image-candidates/tutor_diagnosis/candidate-01.png) | 1376 x 768 (16:9) | Antigravity `generate_image` (`gemini-3.1-flash-image`) | **Owner review pending** |

---

### Detailed Reviews of Batch 4 Candidates

#### 14. Journal Discovery: Research Query Funnel & Access Branching (Candidate 01)

- **Page:** `content/projects/ai-research-assistant/journal_discovery/index.md`
- **Original Brief Path:** `content/projects/ai-research-assistant/journal_discovery/index.md` (Queue row 03)
- **Output File Path:** `docs/editorial/image-candidates/journal_discovery/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 617,916 bytes
- **SHA-256 Digest:** `51076898d883b25692cef71c2acff1769c0d5fa4d67cb80b89e360d0c5fa3634`
- **Original Archive:** `docs/editorial/image-candidates/journal_discovery/original-featured.jpg` (SHA-256: `9381a2faf80812bf4a3afafeacced2d5824b8824b6fbb730f4728ebec567fbbf`, 553,753 bytes)
- **Proposed Caption:** "Finding a relevant paper and obtaining its full text are separate steps."
- **Proposed Alt Text:** "One disaster-research trial narrowed 60 candidates to 15 accepted papers, with seven PDFs downloaded and eight left for manual access."
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow progression representing a research discovery funnel: 1. On the left, a card labelled 'Research Query' with text 'Topic: Disaster Resilience' and subtitle badge 'Dated trial: Oct 15'; 2. A clean arrow leads to a funnel card titled 'Candidate Pool' with text '60 candidates retrieved'; 3. Arrow leads to 'Human Review' card with teal check badge '15 accepted'; 4. Branching arrows lead to two distinct outcome cards on the right: top card with teal badge '7 PDFs downloaded' and bottom card with violet badge '8 manual-access entries'; 5. Discreet bottom tag: 'Single trial outcome, not a general rate'. Balanced 16:9 composition, generous outer margins, crisp sans-serif typography, flat clean vector design.
  ```
- **Visual & Factual Inspection:**
  - **Funnel Progression:** Left-to-right flow from Research Query ("Topic: Disaster Resilience") to Candidate Pool ("60 candidates retrieved").
  - **Human Review Gate:** Central card highlights "Human Review" with a checkmark badge reading "15 accepted".
  - **Access Branching:** Branches clearly into two cards on the right: "7 PDFs downloaded" (teal badge) and "8 manual-access entries" (violet badge).
  - **Single Trial Qualification:** Subtitle badge on the query card notes "Dated trial: Oct 15", and the bottom tag explicitly states: "Single trial outcome, not a general rate", avoiding any claim of a universal success rate.
  - **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 15. Visualization: Gradient Descent Surface & Actual Trajectory (Candidate 01)

- **Page:** `content/projects/academic-hub/visualization/index.md`
- **Original Brief Path:** `content/projects/academic-hub/visualization/index.md` (Queue row 04)
- **Output File Path:** `docs/editorial/image-candidates/visualization/candidate-01.png`
- **Tool / Model:** Rendered mathematical plot using Plotly from `agent/viz/templates/gradient_descent.py` captured via headless Edge
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 240,472 bytes
- **SHA-256 Digest:** `ad8aad6f225bbd36d2a3faf35c6085de62d46073b493c8f3068055d92669a07c`
- **Original Archive:** `docs/editorial/image-candidates/visualization/original-featured.jpg` (SHA-256: `5159cf46af38df9ac81c0ff436fcdb3ddd0b5b26fce712a42c290314772c698a`, 737,246 bytes)
- **Proposed Caption:** "Inspect the steps as they approach the minimum."
- **Proposed Alt Text:** "A gradient-descent path curves across the contours of a bowl-shaped function toward its minimum at the origin."
- **Rendering Specification:**
  - Evaluates the actual objective function $f(x, y) = x^2 + 2y^2$ across an elliptic grid $x, y \in [-4.5, 4.5]$.
  - Computes the numerical gradient descent trajectory starting from $(3.5, 3.0)$ with step size $\alpha = 0.15$ over 25 iterations.
  - Plots genuine elliptic contour lines in teal tones (`#15293E` to `#35C9C8`) on a `#0E1724` plot surface.
  - Plots the discrete descent steps in vibrant violet (`#B794F6`, `#D6BCFA`) showing how steps cross contours orthogonally.
  - Callouts indicate "Start (3.5, 3.0)" (diamond marker) and "Minimum (0, 0)" (star marker) without edge clipping.
  - Right information panel displays an Objective Function card with exact formula $f(x, y) = x^2 + 2y^2$, contour/descent badges, and a Steepest Descent Trajectory explanation card.
  - Bottom badge explicitly attributes: "Rendered from template: gradient_descent.py".
- **Visual & Factual Inspection:**
  - Truly authentic mathematical plot generated directly from code; zero generative diffusion hallucination or fabricated interface elements.
  - High contrast, dark navy background `#14202D`, crisp typography, and balanced 16:9 composition.
- **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 16. Resume Manager: Structured Master Resume to Tailored Draft (Candidate 02)

- **Page:** `content/projects/resume_manager/index.md`
- **Original Brief Path:** `content/projects/resume_manager/index.md` (Queue row 06)
- **Output File Path:** `docs/editorial/image-candidates/resume_manager/candidate-02.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 749,098 bytes
- **SHA-256 Digest:** `9224cd861e511a80ab7ad82a0f9157114b15d496ff8e89284d85bdd21686afcc`
- **Original Archive:** `docs/editorial/image-candidates/resume_manager/original-featured.jpg` (SHA-256: `a9da1fe1f95a1f1d26d7a11fd17f6dff4d4a0ed8afea795dfae00266602fc3ff`, 580,578 bytes)
- **Earlier Candidates:** `candidate-01.png` (779,649 bytes, SHA-256: `e1f50efd...`, replaced due to biological appearance of center icon)
- **Proposed Caption:** "Change the emphasis while keeping the record of experience fixed."
- **Proposed Alt Text:** "A structured master resume supplies fixed facts while a job description guides bullet wording; the resulting draft includes review checks."
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right: 1. On the left, two input cards stacked vertically: top card 'Master Resume' showing fixed fields with violet badges 'Employer: Acme Corp' and 'Dates: 2023–2025'; bottom card 'Job Description' with teal badge 'Requirements: Distributed Systems'; 2. In the center, a processing junction with a teal square node containing a clean geometric mechanical gear icon, topped by a white speech bubble callout 'Parser first; model for wording'; 3. Clean connector arrows lead to two cards on the right: top card 'Tailored Draft' with editable bullet points; bottom card 'Review Report' with check badges 'Fixed facts verified' and 'Validation check: PASS'; 4. At the bottom center, a discreet pill tag: 'Invented applicant profile'. Crisp sans-serif typography, balanced 16:9 composition, generous outer margins, clean flat vector design.
  ```
- **Visual & Factual Inspection:**
  - **Mechanical Gear Icon:** The center node beneath the "Parser first; model for wording" callout bubble now features a crisp, clean geometric gear icon representing code parsing, completely replacing the organic-looking icon from Candidate 01.
  - **Fixed vs. Editable Distinction:** "Master Resume" distinctly separates fixed facts with violet badges ("Employer: Acme Corp", "Dates: 2023–2025"). "Tailored Draft" highlights editable bullet points.
  - **Target Guidance:** "Job Description" specifies "Requirements: Distributed Systems" in teal.
  - **Validation & Privacy:** "Review Report" card includes checkmarks for "Fixed facts verified" and "Validation check: PASS". Bottom tag confirms "Invented applicant profile".
  - **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 17. Video Lecture Notes: Multi-Lecture Synthesis & Timestamp Limits (Candidate 01)

- **Page:** `content/projects/academic-hub/video_notes/index.md`
- **Original Brief Path:** `content/projects/academic-hub/video_notes/index.md` (Queue row 07)
- **Output File Path:** `docs/editorial/image-candidates/video_notes/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 696,833 bytes
- **SHA-256 Digest:** `5a7745fc5180e32e0ad52a644408180818fddfd45cb6e632d2443f943eb11bac`
- **Original Archive:** `docs/editorial/image-candidates/video_notes/original-featured.jpg` (SHA-256: `422a104467d8f8099f4dbc3e68bd3202bca95970aa59caff7788b68e5caeaa22`, 564,761 bytes)
- **Proposed Caption:** "Combine related lectures without losing track of what needs checking."
- **Proposed Alt Text:** "Lecture recordings feed transcripts and a combined study note, with a reminder that precise concept-to-video references are unfinished."
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right: 1. On the left, three stacked video cards labelled 'Lecture 01', 'Lecture 02', and 'Lecture 03' with clean video camera icons; 2. Clean arrows merge into a central card titled 'Timestamped Transcripts' showing two clear dialogue lines: first line with teal badge '04:15' and text 'Recall our definition of a function.'; second line with teal badge '18:30' and text 'A mapping assigns each domain element.'; 3. Arrow leads to a clean card on the right titled 'Study Note: Sets & Functions' with text 'Summary: Injective vs Surjective mappings', with a small badge 'Illustrative note'; 4. Attached to the bottom of the transcript card, a prominent violet callout speech bubble: 'Concept timestamps still incomplete'; 5. Discreet bottom pill tag: 'Illustrative lecture synthesis'. Perfectly legible sans-serif typography, balanced 16:9 composition, generous outer margins, clean flat vector design.
  ```
- **Visual & Factual Inspection:**
  - **Multi-Lecture Input:** Three stacked video cards on the left ("Lecture 01", "Lecture 02", "Lecture 03") with clean camera icons.
  - **Timestamped Transcripts:** Dialogue lines with teal time tags ("04:15: Recall our definition of a function.", "18:30: A mapping assigns each domain element.").
  - **Incomplete Timestamp Callout:** A prominent violet speech bubble reads: "Concept timestamps still incomplete", explicitly documenting the unfinished reference link without falsely claiming granular timestamping.
  - **Study Note Card:** Right card shows "Study Note: Sets & Functions" with summary of injective/surjective mappings and badge "Illustrative note".
  - **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

#### 18. Tutor Diagnosis & Hint Generator: Formative Review & Step Feedback (Candidate 01)

- **Page:** `content/projects/academic-hub/tutor_diagnosis/index.md`
- **Original Brief Path:** `content/projects/academic-hub/tutor_diagnosis/index.md` (Queue row 09)
- **Output File Path:** `docs/editorial/image-candidates/tutor_diagnosis/candidate-01.png`
- **Tool / Model:** Antigravity `generate_image` (`gemini-3.1-flash-image`)
- **Actual Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 833,968 bytes
- **SHA-256 Digest:** `bd30d9f046708f2bdca9bcf9ec9906ec80e3b8ceed7ae9efdd3657821f9912f7`
- **Original Archive:** `docs/editorial/image-candidates/tutor_diagnosis/original-featured.jpg` (SHA-256: `84c01856b93d26aa2617ce049bfeebe02f52f0ac6dae1d89bcdf01aa257ddf90`, 667,603 bytes)
- **Proposed Caption:** "Review the argument, not just its final answer."
- **Proposed Alt Text:** "A student revises an attempt after a hint, then reviews separate feedback on the result, reasoning, and fit with the course."
- **Exact Prompt:**
  ```text
  Clean modern technical editorial diagram on a solid dark navy background (#14202D). High contrast, minimalist graphic illustration with teal (#35C9C8) and muted violet (#A58AE0) accents. Horizontal workflow from left to right: 1. Left card labelled 'Student Attempt' with text 'Claim: (A+B)² = A² + 2AB + B² for matrices A, B'; 2. Arrow leads to a central card labelled 'Tutor Hint' with violet badge 'Hint, not solution' and text 'Check if matrix multiplication commutes: does AB = BA?'; 3. Arrow leads to 'Revised Attempt' card with text 'A² + AB + BA + B² (since AB ≠ BA)'; 4. Stacked beside the revision are three distinct review labels: 'Result: Valid', 'Reasoning: Non-commutative property recognized', and 'Course fit: Linear Algebra standards'; 5. Discreet bottom tag: 'Formative feedback, not grade assessment'. Balanced 16:9 composition, generous outer margins, crisp sans-serif typography, flat clean vector design.
  ```
- **Visual & Factual Inspection:**
  - **Attempt → Hint → Revision Progression:** Clear three-card sequence illustrating student reasoning:
    1. Initial attempt: $(A+B)^2 = A^2 + 2AB + B^2$ for matrices $A, B$.
    2. Tutor hint: "Check if matrix multiplication commutes: does $AB = BA$?" (violet badge "Hint, not solution").
    3. Revised attempt: $A^2 + AB + BA + B^2$ (since $AB \neq BA$).
  - **Three Review Feedback Labels:** Stacked beside the revision:
    - "Result: Valid"
    - "Reasoning: Non-commutative property recognized"
    - "Course fit: Linear Algebra standards"
  - **Formative Framing:** Bottom pill tag clearly notes "Formative feedback, not grade assessment", reinforcing that this is diagnostic guidance rather than formal grading.
  - **Review Status:** **Owner review pending** (Asset preserved under `image-candidates/`; not integrated into page bundle).

---

## Workspace Status and Changes Summary

- **Repository Root:** `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-website-images`
- **Branch:** `gemini/website-images`
- **Committed Local Work:**
  - Commit `ea6faef`: Pilot images integrated for Concept Graph, Source Indexer, Notes Transcription.
  - Commit `d87e78e`: Batch 2 images integrated for Study Guide Pipeline, Summary Enhancement, Guided Solutions, Socratic Tutor, Corpus Health.
  - Commit `8e5056d`: Cherry-pick of original archives for Source Indexer, Notes Transcription, and baseline provenance inventory.
  - Commit `112fd70`: Archive Batch 3 originals, add candidates for steering, marker, postprocess, and source indexer v2.
  - Commit `220bafc`: Add candidate images for rag_analysis and problem_generation.
  - Commit `52a05fe`: Documentation tracking update in generation report.
  - Commit `515745e`: Add Round 2 revised candidate images for Batch 3.
  - Commit `398ec57`: Integrate approved Batch 3 featured images and pilot correction.
- **Active Uncommitted Batch 4 Work (Awaiting Owner Review):**
  - Archived originals for all 5 Batch 4 pages preserved in `image-candidates/*/original-featured.jpg` and recorded in `image-originals-inventory.md`.
  - Five candidate images created in `docs/editorial/image-candidates/`:
    - `docs/editorial/image-candidates/journal_discovery/candidate-01.png`
    - `docs/editorial/image-candidates/visualization/candidate-01.png`
    - `docs/editorial/image-candidates/resume_manager/candidate-01.png`
    - `docs/editorial/image-candidates/video_notes/candidate-01.png`
    - `docs/editorial/image-candidates/tutor_diagnosis/candidate-01.png`
  - Generation report updated with Batch 4 candidate reviews.
- **Integrity Verification:**
  - Zero edits have been made to `content/projects/` page bundles or active featured assets for Batch 4.
  - All original archived files (`original-featured.jpg`) are verified with SHA-256.
  - All `[[Insert Image: ...]]` briefs remain in place awaiting owner review.
  - No branches switched, merged, pushed, or deployed.





