---
title: Audio Generator
date: 2026-09-09
lastmod: 2026-10-16
summary: "Turn notes into spoken episodes, translating mathematical notation into language a speech engine can read."
type: academic-hub-project
image:
  caption: "Illustration: Translate the notation before reading it aloud."
  alt_text: "An expected-value expression becomes spoken language, then three illustrative audio episodes."
  focal_point: Center
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/academic-rag-model/audio_generator
  - type: site
    icon: brands/github
    label: 'Status: Audio Generator'
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/audio_generator/2026-09-09-audio-generator-status.md
tags:
  - Python
  - LLM / RAG
params:
  subproject:
    id: audio_generator
    package: audio_generator
    code_paths:
      - ai-sandbox/academic-rag-model/audio_generator
    readme_path: ai-sandbox/academic-rag-model/audio_generator/README.md
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/audio_generator/2026-09-09-audio-generator-status.md
        role: current
        lifecycle_ids:
          - audio-generator
    members: []
---

Audio Generator turns course notes into MP3 episodes for listening away from a screen. Mathematical notation needs an extra step: a speech engine can read words, but raw formula commands often sound unintelligible. The tool rewrites that notation into spoken language before synthesizing the recording.

<!--more-->

For an **illustrative translation**, E[X] becomes "the expected value of X." Denser equations need more than symbol replacement to preserve what the expression means. The pipeline sends math-heavy passages to a cloud model for that rewrite, while text cleanup and speech synthesis run locally. Plain prose can skip the model call.

Notes are split into episodes targeting 10–20 minutes. The current code can divide oversized sections at paragraph boundaries; one indivisible paragraph may still exceed the target. Textbook inputs follow a different path and currently produce one MP3 per source file. Editing any part of a note regenerates all of that file's episodes; unchanged sources can be skipped.

The September 9, 2026 stress test used one equation-dense, roughly 122,000-character note. It took 3.8 minutes to prepare the narration and another 19.4 minutes to synthesize speech, producing nine files in 23.2 minutes overall. One episode was about 62 minutes long. That historical result predates the paragraph-splitting fix; a new listening test is needed to judge the revised output.

The local model tried earlier took about six hours on the same difficult input. Cloud rewriting reduced the wait but introduced API cost. Its speed does not establish that every formula was explained correctly, so the saved narration text provides something to inspect before relying on the audio.

[Summary Enhancement](/projects/academic-hub/summary_enhancement/) and [Study Guide Pipeline](/projects/academic-hub/study_guide_pipeline/) now exist, but an automatic weekly-summary-to-audio workflow is not established. Notes audio is stored with the larger course resources, outside tablet notes sync. The [README](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/audio_generator/README.md) describes current output and regeneration behavior.
