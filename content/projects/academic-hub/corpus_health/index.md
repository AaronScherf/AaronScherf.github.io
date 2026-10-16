---
title: Corpus Health
summary: "Find gaps between source documents, converted notes, and search records, then review specific repairs before running them."
date: 2026-10-11
lastmod: 2026-10-16
draft: false
type: academic-hub-project
links:
  - type: site
    icon: brands/github
    label: Source code
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/tools/corpus_health
  - type: site
    icon: brands/github
    label: Capability inventory
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-08-corpus-health-capability-inventory.md
  - type: site
    icon: brands/github
    label: Repair adapter decision
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-09-corpus-health-apply-first-adapter-decision.md
  - type: site
    icon: brands/github
    label: Implementation and trial status
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-09-corpus-health-implementation-retrospective.md
tags:
  - Python
  - Corpus Maintenance
params:
  subproject:
    id: corpus_health
    package: tools/corpus_health
    code_paths:
      - ai-sandbox/academic-rag-model/tools/corpus_health
    readme_path: ai-sandbox/academic-rag-model/tools/corpus_health/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-08-corpus-health-capability-inventory.md
        role: historical
        lifecycle_ids:
          - corpus-health
      - path: ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-09-corpus-health-apply-first-adapter-decision.md
        role: current
        lifecycle_ids:
          - corpus-health
      - path: ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-09-corpus-health-implementation-retrospective.md
        role: current
        lifecycle_ids:
          - corpus-health
    members: []
---

Having a converted lecture note on disk does not mean its latest text is available in search. Corpus Health checks for gaps between source documents, converted text, and the [Source Indexer's catalog](/projects/academic-hub/source_indexer/), then presents specific findings for review. It remembers declined or deferred findings so the same unchanged item does not keep appearing as a new problem.

<!--more-->

The repair scope is deliberately small: it can rebuild searchable passages for one identified document whose search record is already current. Before acting, it checks that the document and record still match the reviewed finding. Afterward, it audits the result. A changed source needs another check rather than relying on an old approval.

[[Insert Image: Create a landscape explanatory diagram following one document from "Gap found" to "Owner review", "Repair one document", and "Check result". Show the source document beside its search passages, with a missing passage restored only after review. A separate small branch should say "Changed source: review again". Use generic documents rather than private notes or a fabricated report. Keep the four main labels large enough for a thumbnail. Suggested caption: "Discover a gap, choose a repair, and check the result." Suggested alt text: "A missing search passage is reported for review, repaired for one document, and checked afterward; a changed source returns for review." Save the approved image as featured.jpg or featured.png in this page bundle.]]

For an **illustrative case**, a transcript may have been updated while its searchable passages still reflect the earlier version. The scan flags the mismatch. I can accept, decline, or defer it on a local review page; running accepted repairs is a separate step. Rebuilding those passages can incur an AI embedding charge, so acceptance is recorded for each source.

Keeping those passages current matters to the [study guides](/projects/academic-hub/study_guide_pipeline/) and [concept maps](/projects/academic-hub/concept_graph/) that read them. A missing source may look like a gap in the model's explanation when the material was never available to search.

The scanner itself makes no model calls or edits to course materials. Repair uses a shared lock to coordinate with participating tools, but some writers, including Obsidian sync, do not follow that protocol. They must not write to the same destination during a repair. Transcription, textbook conversion, and broader catalog rebuilds remain outside the enabled repair action.

Initial live scans on October 9, 2026 took about 21–28 seconds, but their roughly 305 findings still needed sample review to distinguish genuine gaps from classification mistakes. A daily discovery-only trial was scheduled for October 10–16. An October 16 read-only check found completed reports for several days alongside empty logs for others; the observation period still needs review before claiming reliable daily operation. The scheduled task performs no repairs.

The [implementation and trial record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-09-corpus-health-implementation-retrospective.md) separates fixture tests from live observations. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/tools/corpus_health/README.md) documents the scan policies and current repair boundary.
