---
title: Obsidian Git Sync
date: 2026-09-21
lastmod: 2026-10-16
summary: "Keep editable notes available on tablet and laptop while large source files stay outside the lightweight sync."
type: academic-hub-project
image:
  caption: "Illustration: Sync the working notes while keeping large sources separate."
  alt_text: "A tablet and laptop share editable notes while a separate source archive feeds transcription and search."
  focal_point: Center
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-21-obsidian-git-sync-status.md
  - type: site
    icon: brands/github
    label: Follow-up notes
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-26-obsidian-git-sync-status.md
  - type: site
    icon: brands/github
    label: Source configuration
    url: https://github.com/AaronScherf/ai-sandbox-master/tree/main/ai-sandbox/.obsidian
tags:
  - Git
  - JavaScript
params:
  subproject:
    id: obsidian_git_sync
    package: obsidian_git_sync (configuration)
    code_paths:
      - ai-sandbox/.obsidian
    readme_path: null
    status_docs:
      - path: ai-sandbox/academic-rag-model/docs/status/2026-09-21-obsidian-git-sync-status.md
        role: historical
        lifecycle_ids:
          - obsidian-sync
      - path: ai-sandbox/academic-rag-model/docs/status/2026-09-26-obsidian-git-sync-status.md
        role: current
        lifecycle_ids:
          - obsidian-sync
    members: []
---

I want to write a lecture note on my tablet and find the editable drawing on my laptop, without bringing the whole textbook archive onto the tablet. This setup uses Obsidian, a notes app, and Excalidraw, its drawing tool. Working notes sync separately from the large source files used to process them.

<!--more-->

The tablet currently uses Fit, which exchanges files through GitHub's API rather than maintaining a local Git history. That avoids the history-download problem that caused trouble with an earlier plugin. The laptop uses Obsidian Git, and some settings remain device-specific.

| Lightweight notes vault | Separate source archive |
| --- | --- |
| Markdown notes, editable Excalidraw scenes, processed text | PDFs, exported drawing images, and generated audio |

Saving an Excalidraw file automatically creates an SVG image. The [transcription tools](/projects/academic-hub/notes_transcription/) use those images to make the handwriting searchable; saving alone does not perform that transcription. The source-relocation record reports the existing course materials moved into the archive, with the tools adapted to find them there while keeping processed text in the notes vault.

Keeping the boundary intact required more than a folder move. An earlier sync plugin rewrote ignore rules from each device's settings, letting PDFs enter the notes history. Removing those large files from the old history reduced its size from about 217 MB to 35 MB. That incident explains the emphasis on separate storage and device settings; the current tablet sync uses a different mechanism.

Customization was another reason I chose this approach. Editing plugin code let me translate a pen menu and add an eraser button. A separate interface-style change moved zoom and undo controls clear of the tablet's gesture bar. Being able to fix those details myself was an advantage over my experience with OneNote.

Fit does not transfer plugin source files, so changes to that customized plugin still need a manual copy to the tablet. The interface-style snippet can sync when explicitly included, but enabling it and other settings may need attention on each device.

Matching handwritten-only notes with later copies containing slides is handled by the [Source Indexer](/projects/academic-hub/source_indexer/). The [sync follow-up](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/status/2026-09-26-obsidian-git-sync-status.md) and [relocation record](https://github.com/AaronScherf/ai-sandbox-master/blob/main/ai-sandbox/academic-rag-model/docs/superpowers/plans/convert_textbook/2026-09-21-source-asset-relocation.md) distinguish the configuration from the completed archive move.
