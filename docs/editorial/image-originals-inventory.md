# Preserved original featured images

Recovered 2026-10-18 from the pre-image-pass baseline
`5096eb48ce3c2e24b4e39117d0a3116266be699f`. No image was regenerated, resized, compressed, or re-encoded.
Both recovered files match the original Git blob IDs and SHA-256 digests.

The active approved page images and the ten existing candidate files are unchanged.
These archives live outside content/ so Hugo cannot select them as featured assets.

## Coverage of all eight updated pages

| Page | Before this image pass | Preserved original |
|---|---|---|
| concept_graph | No featured asset at the baseline; first image added in this pass | Not applicable |
| source_indexer | Existing featured image | [original-featured.jpg](image-candidates/source_indexer/original-featured.jpg) |
| notes_transcription | Existing featured image | [original-featured.jpg](image-candidates/notes_transcription/original-featured.jpg) |
| study_guide_pipeline | No featured asset at the baseline; first image added in this pass | Not applicable |
| summary_enhancement | No featured asset at the baseline; first image added in this pass | Not applicable |
| guided_solutions | No featured asset at the baseline; first image added in this pass | Not applicable |
| socratic_tutor | No featured asset at the baseline; first image added in this pass | Not applicable |
| corpus_health | No featured asset at the baseline; first image added in this pass | Not applicable |

## Original file provenance

### source_indexer

- Original commit: `5096eb48ce3c2e24b4e39117d0a3116266be699f`
- Original path: `content/projects/academic-hub/source_indexer/featured.jpg`
- Archive path: `docs/editorial/image-candidates/source_indexer/original-featured.jpg`
- Size: 516067 bytes
- Git blob ID (original and archive): `124d85ca341bf4c62ba5d99c9192eec252f970c4`
- SHA-256: `6f6f58b6c54d81e0071ce126ffc8ff966c79e789b4da0636bc4f8f8772dc7667`
- Verification: exact byte comparison and Git blob identity passed.

### notes_transcription

- Original commit: `5096eb48ce3c2e24b4e39117d0a3116266be699f`
- Original path: `content/projects/academic-hub/notes_transcription/featured.jpg`
- Archive path: `docs/editorial/image-candidates/notes_transcription/original-featured.jpg`
- Size: 519048 bytes
- Git blob ID (original and archive): `8c27f00a1ff03a0cd372448d22752a4492ffddb2`
- SHA-256: `75ad2fc6ce2db57e79ea4ff4cb1fb632dbe14619cdf3f704da13c0521a5bbfe9`
- Verification: exact byte comparison and Git blob identity passed.

## Earlier generated alternatives

All ten existing files beneath `docs/editorial/image-candidates/` are already
tracked on the Gemini image branch. This includes both Concept Graph candidates
and both Notes Transcription candidates. A rejected candidate is an alternative
generated during this pass, not an original featured asset.

The pilot is committed at `ea6faef`; Batch 2 is committed at `d87e78e`.
This inventory does not add, infer, or change any owner approval.

## Reverting later

Keep these originals immutable. Before replacing any active approved image,
retain its exact bytes as a separately numbered version in the candidate folder.
After the owner chooses a version, copy that image into the page bundle, update
its caption/alt text to match, ensure one active featured asset, and check the
rendered article and card. Do not keep backup names containing featured in a
page bundle; the theme searches that wildcard.

Future replacements must preserve their current featured image in their candidate
folder before integration. If an original archive already exists, verify its
identity and preserve it; never overwrite it with a newer image. Track later
approved versions under distinct names and retain all earlier candidates.

## Recovery scope and verification

- Two original JPG files recovered; six pages correctly recorded as having
  no pre-pass featured asset.
- Only the two archives and this inventory are part of the recovery commit.
- No active page, current image, candidate, source repository, or owner decision
  was changed. No merge or push was performed.
- Hash verification establishes preservation of the original files. It does
  not establish anything about the depicted software or mathematical claims.
