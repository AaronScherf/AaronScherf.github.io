# Project Page Featured Image Candidates Report

**Date:** 2026-11-10  
**Branch:** `gemini/project-page-images`  
**Worktree:** `C:/Users/theaa/ai-sandbox-master/.worktrees/gemini-project-page-images`  
**Status:** **Approved by owner; integrated into page bundles as `featured.png`**  

This report documents the candidate featured illustrations generated, revised, and integrated for two project pages currently on PR #4 (`claude/projects-reprokit-compound-shocks`):
- `content/projects/compound_shocks/index.md`
- `content/projects/reprokit/index.md`

All candidate assets are 1376 x 768 PNGs adhering to the site's editorial house style (navy `#14202D`, teal `#35C9C8`, and restrained violet `#A58AE0` on a plain light background) with strict adherence to the negative and positive constraints of each page's brief. Generated illustrations used Antigravity's native image capability under the owner's subscription; no paid third-party API was used.

Following explicit owner approval, both approved images have been integrated into their respective Hugo page bundles as `featured.png`, frontmatter `image:` metadata has been updated with verified captions, alt text, and `focal_point: Center`, and the fulfilled `# TODO(image)` comment blocks have been removed.

---

## Candidate and Integration Summary

| Page | Candidate Path | Integrated Asset Path | Dimensions | File Size | SHA-256 Digest | Status |
|---|---|---|---|---|---|---|
| **Compound Shocks Panel** | `docs/editorial/image-candidates/compound_shocks/featured-candidate.png` | `content/projects/compound_shocks/featured.png` | 1376 x 768 (16:9) | 761,448 B | `1c4c49cfeefa966fb77df9d9cd025de3279adba460fae1653604b06055662d5f` | **Approved by owner & integrated** |
| **reprokit (Candidate 01)** | `docs/editorial/image-candidates/reprokit/featured-candidate-01.png` | — | 1376 x 768 (16:9) | 651,699 B | `2766d6dd90b8f1a95e0fcd8076b5d3c579ba6b752ecb63f764149b44558fe1f6` | **Superseded by Candidate 02** |
| **reprokit (Candidate 02)** | `docs/editorial/image-candidates/reprokit/featured-candidate-02.png` | — | 1376 x 768 (16:9) | 753,683 B | `308c65348e0f62924e5345cd1b25ba83a12926bf400b4cd28e8bd995dedbb123` | **Superseded by Candidate 03** |
| **reprokit (Candidate 03)** | `docs/editorial/image-candidates/reprokit/featured-candidate-03.png` | — | 1376 x 768 (16:9) | 811,228 B | `f8b170428a064e614bd2729bfb6279423f0d4d16fe6494c3682c2d5b9d6c0f0b` | **Superseded by Candidate 04** |
| **reprokit (Candidate 04 / Final)** | `docs/editorial/image-candidates/reprokit/featured-candidate.png` | `content/projects/reprokit/featured.png` | 1376 x 768 (16:9) | 804,627 B | `a52c737c58447989052a0b710b7b99b5c4273ae276b9d7b895d2c56dd0763239` | **Approved by owner & integrated** |

---

## Detailed Integration Documentation

### 1. Compound Shocks Panel

- **Source Page:** `content/projects/compound_shocks/index.md`
- **Integrated Page Bundle Asset:** `content/projects/compound_shocks/featured.png`
- **Candidate Archive:** `docs/editorial/image-candidates/compound_shocks/featured-candidate.png`
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio, PNG)
- **File Size:** 761,448 bytes
- **SHA-256 Digest:** `1c4c49cfeefa966fb77df9d9cd025de3279adba460fae1653604b06055662d5f`
- **Integrated Frontmatter:**
  ```yaml
  image:
    caption: "Illustration: Four separate sources are lined up into one district-by-month table, with the restricted raw conflict records kept out of what is shared."
    alt_text: "Four labelled inputs (conflict events, rainfall, food prices, displacement) feed a grid of districts by months. A lock marks the raw conflict records as kept private, and only district-month totals leave the grid."
    focal_point: Center
  ```
- **Visual & Factual Elements:**
  - Four labelled inputs on left: `"Conflict events"`, `"Rainfall"`, `"Food prices"`, and `"Displacement"` with separated `"people present (stock)"` and `"people moving (flow)"` pills.
  - Central `"District x month"` table showing sparse colored markers and empty cells ("missing stays missing").
  - Stack of `"raw conflict records (stay private)"` documents with padlock, and single thin arrow to `"district-month totals (shared)"` table.
  - Bottom strip reading `"rebuild matches"`.
  - Zero real maps, numbers, place names, logos, or results claims.
- **Integration Status:** **Completed** — image copied to `content/projects/compound_shocks/featured.png`, frontmatter updated with `focal_point: Center`, and `# TODO(image)` block removed.

---

### 2. reprokit

- **Source Page:** `content/projects/reprokit/index.md`
- **Integrated Page Bundle Asset:** `content/projects/reprokit/featured.png`
- **Candidate Archive:** `docs/editorial/image-candidates/reprokit/featured-candidate.png` (and `featured-candidate-04.png`)
- **Dimensions:** 1376 x 768 pixels (16:9 landscape aspect ratio, PNG)
- **File Size:** 804,627 bytes
- **SHA-256 Digest:** `a52c737c58447989052a0b710b7b99b5c4273ae276b9d7b895d2c56dd0763239`
- **Integrated Frontmatter:**
  ```yaml
  image:
    caption: "Illustration: A standard project format bridges complete machine reproduction with human and agent readable documentation, verifying identical replication between researcher and user."
    alt_text: "A standard project format holding source descriptors, protocol, config, and README branches into human/agent readable docs and automated rebuilds, verifying exact replication between researcher and user laptops."
    focal_point: Center
  ```
- **Visual & Factual Elements:**
  - Left: `"Standard Project Format"` folder containing `"Source descriptors"`, `"Protocol"`, `"Config"`, `"README"`, tagged with `"Reproducible research adopting best practices in a flexible format"`.
  - Centre: Clean navy branching arrows leading to dual balanced cards:
    - `"Human & Agent Readable"` with reader/AI-agent icons and `"accessible to newcomers & AI agents"`.
    - `"Complete Reproduction"` with `"PASS"` badge, `"hash: a3f9...c21"`, and `"automated deterministic rebuild"`.
  - Right: Continuous connector to top laptop `"Researcher"` and bottom laptop `"User"`, both displaying matching fake hash `"a3f9...c21"`, connected by `=` with label `"identical hash verifies replication succeeded exactly"`.
  - Bottom: Spanning banner `"Balancing human clarity with complete machine reproduction"`.
  - Zero code, terminal screenshots, platform logos, or real cryptographic hashes.
- **Integration Status:** **Completed** — image copied to `content/projects/reprokit/featured.png`, frontmatter updated with verified caption, alt text, and `focal_point: Center`, and `# TODO(image)` block removed.
