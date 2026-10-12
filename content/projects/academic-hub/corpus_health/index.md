---
title: Corpus Health
date: 2026-10-11
draft: true
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

Corpus Health scans a configured academic corpus for missing outputs, Markdown policy gaps, index inconsistencies, and repository-state issues. Its report separates discovery from a person's decision to act.

<!--more-->

The scanner reads explicit roots and policies and makes no model call or corpus edit. A local ledger keeps recurring findings and review decisions stable across runs. A short-lived local review page records accept, decline, or defer decisions. Review itself performs no repair. `apply --accepted` rechecks the target and records a result for each accepted finding. The only enabled repair adapter is an exact-card passage-chunk operation under a cooperative writer lock, followed by an index audit; it may incur embedding API cost. Other repairs remain blocked.

Fixture tests cover scanner, review, lock, and apply behavior. Initial live read-only scans completed in about 21–28 seconds with no scan errors, but their roughly 305 findings were not all individually classified. A discovery-only daily scheduler trial was installed for October 10–16; its multi-day observation and finding sample review were still open in the [trial handoff](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/academic_hub/2026-10-09-corpus-health-implementation-retrospective.md). The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/tools/corpus_health/README.md) details scope and writer coverage.
