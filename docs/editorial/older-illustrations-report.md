# Older Website Illustrations Editorial Correction Report

> **Owner Approval & Integration Handoff, October 20, 2026:** All nine Candidate 01 replacement images have been reviewed and approved by the owner for integration into the website. The task branch `gemini/older-image-corrections` is prepared and handed back to Codex for the final landing and publication pass (replacing `featured.jpg` / installing `featured.png` in page bundles, updating frontmatter image parameters and alt text, verifying builds, and deploying). All nine original `featured.jpg` assets remain preserved in `image-candidates/<slug>/original-featured.jpg`.

**Date:** 2026-10-20
**Branch:** `gemini/older-image-corrections`
**Worktree:** `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-older-image-corrections`
**Status:** **All 9 replacement candidates approved by owner for integration** (all 9 original `featured.jpg` files preserved).

This report documents the replacement candidates generated for all nine older website illustrations identified in [`docs/editorial/live_site_readiness_audit_2026-10-19.md`](live_site_readiness_audit_2026-10-19.md). All work was executed in accordance with the site's [`CLAUDE.md`](../../CLAUDE.md), [`docs/AGENT_ROUTING.md`](../AGENT_ROUTING.md), and workspace instructions.

Per instructions:
- For each page bundle, the existing `featured.jpg` was copied unchanged to `docs/editorial/image-candidates/<slug>/original-featured.jpg`.
- Completed replacements are saved as `candidate-01.png` in each candidate directory.
- No page content or frontmatter was modified; no live `featured.jpg` was replaced; nothing was merged, pushed, or deployed.
- All nine candidate images have been visually inspected at full resolution and mobile thumbnail scale, verified against source claims, and recorded below with dimensions and SHA-256 hashes.

---

## Candidate Summary Table

| # | Slug | Page Path | Original Image (Preserved) | Candidate 01 Path | Dimensions | File Size | SHA-256 Digest | Status |
|---|---|---|---|---|---|---|---|---|
| 1 | `pedagogical_rag_hints` | `content/blog/pedagogical_rag_hints/index.md` | [`original-featured.jpg`](image-candidates/pedagogical_rag_hints/original-featured.jpg) | [`candidate-01.png`](image-candidates/pedagogical_rag_hints/candidate-01.png) | 1376 x 768 (16:9) | 729,924 B | `4de52621193f9d6e2c16e19a8a9dfe37a431e6696a45d722a58c38f24a6e3652` | **Approved by owner** (Ready for Codex integration) |
| 2 | `textbook_conversion_automation` | `content/blog/textbook_conversion_automation/index.md` | [`original-featured.jpg`](image-candidates/textbook_conversion_automation/original-featured.jpg) | [`candidate-01.png`](image-candidates/textbook_conversion_automation/candidate-01.png) | 1376 x 768 (16:9) | 743,342 B | `db8393149271457a22b52ded56b8b06504a3bdf58561229d299770e26956b493` | **Approved by owner** (Ready for Codex integration) |
| 3 | `indexer_and_rag_progress` | `content/blog/indexer_and_rag_progress/index.md` | [`original-featured.jpg`](image-candidates/indexer_and_rag_progress/original-featured.jpg) | [`candidate-01.png`](image-candidates/indexer_and_rag_progress/candidate-01.png) | 1376 x 768 (16:9) | 869,586 B | `4d77662506de18ac539ba8285bbe500c5c716acbb63d2d336e7c98f0862a3e02` | **Approved by owner** (Ready for Codex integration) |
| 4 | `site_management` | `content/blog/site_management/index.md` | [`original-featured.jpg`](image-candidates/site_management/original-featured.jpg) | [`candidate-01.png`](image-candidates/site_management/candidate-01.png) | 1376 x 768 (16:9) | 720,900 B | `8952dfd2a0d8a15af3e9d6864b66c194bb6a2710531c674970a8312515a82353` | **Approved by owner** (Ready for Codex integration) |
| 5 | `ai-research-assistant-overview` | `content/projects/ai-research-assistant-overview/index.md` | [`original-featured.jpg`](image-candidates/ai-research-assistant-overview/original-featured.jpg) | [`candidate-01.png`](image-candidates/ai-research-assistant-overview/candidate-01.png) | 1376 x 768 (16:9) | 826,986 B | `39fcf0d551940c452047130ee3d2f7e7d6a03c8bf4f27503b17ca96d483f98e7` | **Approved by owner** (Ready for Codex integration) |
| 6 | `obsidian_excalidraw_notes` | `content/blog/obsidian_excalidraw_notes/index.md` | [`original-featured.jpg`](image-candidates/obsidian_excalidraw_notes/original-featured.jpg) | [`candidate-01.png`](image-candidates/obsidian_excalidraw_notes/candidate-01.png) | 1376 x 768 (16:9) | 791,568 B | `55211e6c97e92d836d4d9226f0051d6f5be1101ba7ce91e87b91862d40c31de0` | **Approved by owner** (Ready for Codex integration) |
| 7 | `academic_resource_progress` | `content/blog/academic_resource_progress/index.md` | [`original-featured.jpg`](image-candidates/academic_resource_progress/original-featured.jpg) | [`candidate-01.png`](image-candidates/academic_resource_progress/candidate-01.png) | 1376 x 768 (16:9) | 889,093 B | `6e9ab4c2178fbbd90313b38f4db5f6f3aa2e9b5b27b63fe687f76c5d5b8d8e92` | **Approved by owner** (Ready for Codex integration) |
| 8 | `academic_journal_discovery` | `content/blog/academic_journal_discovery/index.md` | [`original-featured.jpg`](image-candidates/academic_journal_discovery/original-featured.jpg) | [`candidate-01.png`](image-candidates/academic_journal_discovery/candidate-01.png) | 1024 x 572 (16:9) | 782,843 B | `de880edd57425016f90028c80e222972b2d04ef7bf03a4c27afb9cd3aa28646f` | **Approved by owner** (Ready for Codex integration) |
| 9 | `academic_hub_infrastructure_cleanup` | `content/blog/academic_hub_infrastructure_cleanup/index.md` | [`original-featured.jpg`](image-candidates/academic_hub_infrastructure_cleanup/original-featured.jpg) | [`candidate-01.png`](image-candidates/academic_hub_infrastructure_cleanup/candidate-01.png) | 1024 x 572 (16:9) | 941,153 B | `cddfdb35f839ce80cc9f001b3df9db5eb06a8139ea68ff5de8266bc2234daaad` | **Approved by owner** (Ready for Codex integration) |

---

## Detailed Candidate Documentation

### 1. Pedagogical RAG Hints (`pedagogical_rag_hints`)

- **Page Path:** `content/blog/pedagogical_rag_hints/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/pedagogical_rag_hints/original-featured.jpg` (681,676 bytes, SHA-256: `6bba5c19c13ad8564fcbf0bc6fa6314c84e69888bfcad725e509f0e31a1ff859`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/pedagogical_rag_hints/candidate-01.png`
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 729,924 bytes
- **SHA-256 Digest:** `4de52621193f9d6e2c16e19a8a9dfe37a431e6696a45d722a58c38f24a6e3652`
- **Palette & Style:** Solid dark navy background (`#14202D`), dark slate container cards (`#1E2D3D`), vibrant teal (`#35C9C8`) and muted violet (`#A58AE0`) accents.
- **Visible Labels:**
  - Left card: `Student Question` / `Concept question on course material`
  - Top branch card (teal accent): `Tutor Hint` / `Suggests a direction without giving the solution`
  - Bottom branch card 1: `Student Attempt` / `Student draft reasoning`
  - Bottom branch card 2 (violet accent): `Attempt Review` / `Checks reasoning steps and course alignment`
- **Audit & Source Alignment:**
  - Audit requirement: *"Replace it with one question branching into a hint and a separate check of the student's attempt; show no proof steps, scores, or fabricated interface."*
  - Checks confirmed: Zero fabricated mathematical proofs (e.g. earlier `Assume sqrt(2) is rational...`), zero garbled text (`LEARN IN MING`), zero numeric rubric scores (`(75%) Correctness`), zero simulated chat or browser frames. Clear, legible sans-serif typography at both full resolution and mobile thumbnail scale.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

### 2. Textbook Conversion Automation (`textbook_conversion_automation`)

- **Page Path:** `content/blog/textbook_conversion_automation/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/textbook_conversion_automation/original-featured.jpg` (750,726 bytes, SHA-256: `e97dca3fe0a7537051956dc0cf0caf7dcdbbce3e1dbb5a14395d9d46c62511ad`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/textbook_conversion_automation/candidate-01.png`
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 743,342 bytes
- **SHA-256 Digest:** `db8393149271457a22b52ded56b8b06504a3bdf58561229d299770e26956b493`
- **Palette & Style:** Solid dark navy background (`#14202D`), dark slate cards (`#1E2D3D`), teal (`#35C9C8`) and muted violet (`#A58AE0`) accents.
- **Visible Labels:**
  - Step 1: `Duplicate Detection` / `Content fingerprint checks for prior conversion`
  - Step 2: `Reuse or Review` / `Reuse existing output or queue for review`
  - Step 3: `Batch Conversion` / `Supervised execution`
  - Branch 1 (teal card): `Completed Text` / `Markdown and page records`
  - Branch 2 (violet card): `Supervised Recovery` / `Operator procedure: reset retry or larger machine`
- **Audit & Source Alignment:**
  - Audit requirement: *"Show duplicate detection, reuse or review, and supervised recovery from a memory failure. A person or coding agent follows the procedure; do not depict automatic VM scaling or on-call alerts."*
  - Checks confirmed: Removed all ungrounded cloud architecture ("Automated OOM Escalation Ladder", "Dynamic VM Resize Cloud APIs AWS/Azure", PagerDuty/Slack on-call alerts, and 12 database icons). Accurately illustrates duplicate detection via content fingerprinting, reuse/review, and operator/agent procedure for memory failure recovery. 100% clean typography and aligned connector arrows.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

### 3. Indexer and RAG Progress (`indexer_and_rag_progress`)

- **Page Path:** `content/blog/indexer_and_rag_progress/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/indexer_and_rag_progress/original-featured.jpg` (647,875 bytes, SHA-256: `71d8299f24b74feeb3e5bcb2139846761549990e427a1771db08c0dceeb93d49`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/indexer_and_rag_progress/candidate-01.png`
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 869,586 bytes
- **SHA-256 Digest:** `4d77662506de18ac539ba8285bbe500c5c716acbb63d2d336e7c98f0862a3e02`
- **Palette & Style:** Solid dark navy background (`#14202D`), dark slate cards (`#1E2D3D`), teal (`#35C9C8`) and muted violet (`#A58AE0`) borders and accents.
- **Visible Labels:**
  - Card 1 (teal border): `Course & Document Narrowing` / `Filters collection to relevant course and documents`
  - Card 2 (violet border): `Passage Retrieval` / `Ranks passages and limits contribution per source`
  - Card 3 (teal accent): `Sourced Answer` / `Answer synthesized with generic [Source A] and [Source B] markers`
- **Audit & Source Alignment:**
  - Audit requirement: *"Show course/document narrowing, passage retrieval, and an answer with generic source markers. No invented answer text, mathematics, or book/page citations."*
  - Checks confirmed: Replaced simulated terminal window filled with garbled mathematics ("conneceedly onemicatedy on symmetric symmetric...") and unverified specific citations (`[Axler p. 157, Thm 7.9]`, `[Simon p. 204]`). Clearly depicts two-stage narrowing, passage ranking with contribution limits per source, and generic `[Source A]` / `[Source B]` markers.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

### 4. Site Management (`site_management`)

- **Page Path:** `content/blog/site_management/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/site_management/original-featured.jpg` (524,945 bytes, SHA-256: `7980db396667d835b53677f5f150e1815afa057113538e686d0b5716919d0b43`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/site_management/candidate-01.png`
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 720,900 bytes
- **SHA-256 Digest:** `8952dfd2a0d8a15af3e9d6864b66c194bb6a2710531c674970a8312515a82353`
- **Palette & Style:** Solid dark navy background (`#14202D`), four dark slate cards (`#1E2D3D`), teal and violet header accents.
- **Visible Labels:**
  - Card 1: `Markdown Edit` / `Authoring content and frontmatter`
  - Card 2: `Human Review` / `Inspect diff and approve changes`
  - Card 3: `GitHub Actions Build` / `Automated Hugo build and index`
  - Card 4: `Published Page` / `Live site updated on GitHub Pages`
- **Audit & Source Alignment:**
  - Audit requirement: *"Show Markdown edit → human review → GitHub Actions build → published page. No fake browser content, contact details, or terminal transcript."*
  - Checks confirmed: Completely eliminates the fake terminal window, simulated git diff transcript, and mock browser window with placeholder Latin text ("lorem ipsum...") and fabricated email addresses. Four-step clean linear editorial diagram showing the real authoring and publishing workflow.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

### 5. AI Research Assistant Overview (`ai-research-assistant-overview`)

- **Page Path:** `content/projects/ai-research-assistant-overview/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/ai-research-assistant-overview/original-featured.jpg` (721,935 bytes, SHA-256: `5080f1aeb14cd552ef790a1a6b8db237c1fa55f0f1a70facc735c21e568d6bdc`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/ai-research-assistant-overview/candidate-01.png`
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 826,986 bytes
- **SHA-256 Digest:** `39fcf0d551940c452047130ee3d2f7e7d6a03c8bf4f27503b17ca96d483f98e7`
- **Palette & Style:** Solid dark navy background (`#14202D`), dark slate cards (`#1E2D3D`), teal and violet accent lines.
- **Visible Labels:**
  - Input Card 1 (teal accent): `Paper Discovery` / `Candidate search and relevance scoring`
  - Input Card 2 (violet accent): `Article Conversion` / `PDF extraction and page tracking`
  - Input Card 3 (violet accent): `Research-Note Conversion` / `Document conversion and study notes`
  - Central Card (teal border): `Source Indexer` / `Cross-collection passage indexing`
  - Output Card (violet accent): `Searchable Research Collection` / `Unified query across papers and notes`
- **Audit & Source Alignment:**
  - Audit requirement: *"Show paper discovery, article conversion, and research-note conversion feeding the Source Indexer and searchable research collection. No invented faculty names or unsupported architecture."*
  - Checks confirmed: Completely removes fabricated faculty names ("Hanar Admin", "Daner Stoners", "Daner Dlaitrman"), 5-tier download waterfall, and federated vector cube graphics. Accurately portrays the three actual workflow inputs converging into the Source Indexer to populate the unified Searchable Research Collection.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

### 6. Obsidian and Excalidraw Notes (`obsidian_excalidraw_notes`)

- **Page Path:** `content/blog/obsidian_excalidraw_notes/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/obsidian_excalidraw_notes/original-featured.jpg` (683,947 bytes, SHA-256: `126952af1e60c8a43248cd4c1ab23a1d3d51d655e9491fbad28336e46120ed6a`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/obsidian_excalidraw_notes/candidate-01.png`
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 791,568 bytes
- **SHA-256 Digest:** `55211e6c97e92d836d4d9226f0051d6f5be1101ba7ce91e87b91862d40c31de0`
- **Palette & Style:** Solid dark navy background (`#14202D`), dark slate cards (`#1E2D3D`), teal and muted violet borders and arrows.
- **Visible Labels:**
  - Upper row (teal border):
    - `Automatic SVG Export` / `Drawing exported on save`
    - Arrow → `Transcription Pipeline` / `Converts handwriting to searchable text`
  - Lower row (violet border):
    - `Editable Plugin Code` / `Source code modifications`
    - Arrow → `Adapted Tablet Controls` / `Custom eraser button and gesture margins`
- **Audit & Source Alignment:**
  - Audit requirement: *"Show automatic SVG export when saving, transcription into searchable text, and editable plugin code used to adapt tablet controls. No equations."*
  - Checks confirmed: Zero garbled equations or formulas (eliminated earlier formulas like `math = 2x^2 + O...`). Clean two-tier layout separating note processing from plugin code customization. Perfect spelling of `Plugin` verified at 100% resolution.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

### 7. Academic Resource Progress (`academic_resource_progress`)

- **Page Path:** `content/blog/academic_resource_progress/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/academic_resource_progress/original-featured.jpg` (558,576 bytes, SHA-256: `320f5d682c1e0a4035fad5a667d2ae85a6212e240ca258f0f35af67d1ed3bdad`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/academic_resource_progress/candidate-01.png`
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio)
- **File Size:** 889,093 bytes
- **SHA-256 Digest:** `6e9ab4c2178fbbd90313b38f4db5f6f3aa2e9b5b27b63fe687f76c5d5b8d8e92`
- **Palette & Style:** Solid dark navy background (`#14202D`), dark slate cards (`#1E2D3D`), teal and muted violet borders and arrows.
- **Visible Labels:**
  - Upper row (Textbook Pipeline, teal borders):
    - `Textbook Conversion` / `Printed page tracking and folio alignment`
    - Arrow → `Figure Descriptions` / `Searchable descriptions for diagrams`
  - Lower row (Notes Pipeline, muted violet borders):
    - `Tiered Transcription` / `Routes between local extraction and AI`
    - Arrow → `Notation Repair` / `Reconstructs superscripts and notation`
- **Audit & Source Alignment:**
  - Audit requirement: *"Show textbook conversion with page tracking and figure descriptions alongside tiered transcription and notation repair for notes. No malformed labels or unsupported cloud setup."*
  - Checks confirmed: Removed malformed labels (earlier `SUITABLE PAGES BY PYMUPDF FONT BASELINES`, misspelled `CORRUPTED OR HANDWWITTEN PAGES`) and unsupported cloud infrastructure (`EPHEMERAL GOOGLE CLOUD GPU VM`). Two clean parallel rows depict textbook conversion (printed/PDF page tracking, figure descriptions) and note transcription (tiered extraction routing, notation repair) with 100% accurate spelling and high contrast.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

### 8. Academic Journal Discovery (`academic_journal_discovery`)

- **Page Path:** `content/blog/academic_journal_discovery/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/academic_journal_discovery/original-featured.jpg` (636,777 bytes, SHA-256: `968c643cd05db8c36af4d6eb2d73edd321f4035f41e4ffca4506b7cfc8632ff2`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/academic_journal_discovery/candidate-01.png`
- **Dimensions:** 1024 x 572 pixels (16:9 landscape aspect ratio)
- **File Size:** 782,843 bytes
- **SHA-256 Digest:** `de880edd57425016f90028c80e222972b2d04ef7bf03a4c27afb9cd3aa28646f`
- **Palette & Style:** Solid dark navy background (`#14202D`), dark slate cards (`#1E2D3D`), vibrant teal (`#35C9C8`) and muted violet (`#A58AE0`) accents.
- **Visible Labels:**
  - Overall Header: `ACADEMIC PAPER DISCOVERY PIPELINE`
  - Card 1 (teal border): `OpenAlex Candidates` / `Catalog search by topic or author`
  - Card 2: `Local Relevance Scoring` / `Offline model scores candidate abstracts`
  - Card 3 (violet header): `Owner Review` / `Inspects and approves reading list`
  - Upper Branch (teal header): `Full-Text Retrieval` / `Available open copies downloaded`
  - Lower Branch (violet header): `Manual-Access Queue` / `Worklist for university library access`
  - Final Card (teal border): `Document Conversion` / `Text added to searchable research library`
- **Audit & Source Alignment:**
  - Audit requirement: *"Show OpenAlex candidates → local relevance scoring → owner review → available full-text retrieval or manual-access queue → conversion. Keep named download services out unless verified against the code."*
  - Checks confirmed: Entirely eliminates the unverified 5-tier download waterfall naming unverified services (`Unpaywall`, `Semantic Scholar`, `CORE.ac.uk`, `arXiv`, `Columbia EZproxy (scraping)`), simulated Cloudflare / bot challenges, and illegible thumbnail text. Depicts a crisp, verified 5-stage sequential flow with clear distinction between open downloads and manual library access.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

### 9. Academic Hub Infrastructure Cleanup (`academic_hub_infrastructure_cleanup`)

- **Page Path:** `content/blog/academic_hub_infrastructure_cleanup/index.md`
- **Original Asset Preserved:** `docs/editorial/image-candidates/academic_hub_infrastructure_cleanup/original-featured.jpg` (553,104 bytes, SHA-256: `aca3053c51ecbf9ba6b5e09e3472a0b123be5c109a3412aca515415c0fbfbf77`)
- **Candidate 01 Path:** `docs/editorial/image-candidates/academic_hub_infrastructure_cleanup/candidate-01.png`
- **Dimensions:** 1024 x 572 pixels (16:9 landscape aspect ratio)
- **File Size:** 941,153 bytes
- **SHA-256 Digest:** `cddfdb35f839ce80cc9f001b3df9db5eb06a8139ea68ff5de8266bc2234daaad`
- **Palette & Style:** Solid dark navy background (`#14202D`), dark slate cards (`#1E2D3D`), teal (`#35C9C8`) and muted violet (`#A58AE0`) panel borders.
- **Visible Labels:**
  - Overall Header: `ACADEMIC HUB INFRASTRUCTURE CLEANUP & HISTORY REDUCTION`
  - Left Panel (teal outline): `Notes History Reduction`
    - Top Card: `Repository Split`
    - Highlight Pill: `Notes history reduced from ~217 MB to 35 MB`
    - Context: `Large PDFs removed from sync history for fast tablet syncing`
    - Arrow down →
    - Bottom Card: `Heavy Source Archive` / `Textbook PDFs and media stored in separate storage`
  - Right Panel (violet outline): `Code Modularization`
    - Card: `Modular Packages` / `Tools grouped by functional role instead of flat folders`
    - Neatly indented package badges with folder icons:
      - `pipelines/ — Conversion & transcription`
      - `discovery/ — Paper search & scoring`
      - `agent/ — Tutoring & hint generation`
      - `core/ — Shared indexing & utilities`
- **Audit & Source Alignment:**
  - Audit requirement: *"Show the documented notes-history reduction from about 217 MB to 35 MB, separation of heavy source files, and code grouped by function. Keep it readable at article width."*
  - Checks confirmed: Replaces the crowded, low-contrast original containing typos (*"Fit GitHub API"*, *"Store heaiy data"*) and a chaotic pile of 15 overlapping folders. Displays a clean, balanced two-column side-by-side design that remains completely legible at standard article width and thumbnail scale.
- **Status:** **Approved by owner**; ready for Codex integration and publication.

---

## Verification & Integrity Checklist

- [x] Dedicated task worktree initialized under `.worktrees/gemini-older-image-corrections` on branch `gemini/older-image-corrections` from `main` (`e2788e6`).
- [x] No writes to main repository checkout.
- [x] All 9 original `featured.jpg` assets copied unchanged to `image-candidates/<slug>/original-featured.jpg` and verified against source SHA-256 hashes.
- [x] All 9 replacement candidates generated in 16:9 PNG format.
- [x] Every generated image inspected at full resolution and thumbnail scale for label accuracy, spelling, and alignment.
- [x] All 9 Candidate 01 illustrations reviewed and approved by the owner.
- [x] Zero changes made to page frontmatter, markdown content, or live `featured.jpg` files.
- [x] Branch prepared for handoff to Codex for final page bundle integration and publication.
- [x] All completed candidates and report staged with explicit file paths and committed.
