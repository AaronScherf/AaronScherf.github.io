---
title: "Turning Dense Math Notes into Commute Podcasts"
summary: "Building audio from mathematical notes meant translating formulas first, then discovering that a valid recording could still be far too long."
date: 2026-10-01
lastmod: 2026-10-16
authors:
  - me
tags:
  - Academic Hub
  - Python
  - Audio / TTS
  - LLM / RAG
image:
  caption: "Mathematical notation is rewritten for speech before notes become separate audio episodes."
---

I built the [Audio Generator](/projects/academic-hub/audio_generator/) to make course notes available away from a screen. Reading a mathematical document aloud requires more than sending its text to a speech engine: formula commands need to become spoken language first. As an illustrative example, E[X] should become "the expected value of X," not a recital of brackets and formatting commands.

<!--more-->

The first complete recording exposed a different problem: it was three hours and 22 minutes long. Generating a valid MP3 had solved file production, but left navigation through a long set of notes unresolved. I changed the output to separate episodes grouped around headings, with an index showing which sections went into each file.

[[Insert Image: Show a long audio timeline labelled "3 hours 22 minutes" beside an episode list from the historical nine-file trial. Mark one episode "about 62 minutes" and the others simply by section, without inventing durations. Add a small E[X] to "expected value of X" translation inset. Suggested caption: "Producing the recording was only the first step." Suggested alt text: "A long recording becomes separate episode files; the historical trial still includes one oversized episode, and notation is translated before speech synthesis." Save the approved replacement as featured.jpg or featured.png in this page bundle.]]

*This October 1, 2026 post describes the September development run. The dated update below separates later changes from that result.*

## Translate the notation before speaking

Simple replacements left too much raw formula syntax behind. A local model could rewrite the notation, but the recorded test on a roughly 122,000-character note took about six hours. The next version sent mathematical passages to cloud models while leaving plain prose alone. Cleanup and speech synthesis stayed local.

The amount of notation determined which model handled each passage. Shorter requests could run concurrently, and a later change let sections share one dispatch queue rather than waiting for each section in turn. That brought preparation of the narration text to 3.8 minutes in the September 9 run.

## Separate preparation from production

Speech synthesis took another 19.4 minutes with three local Piper workers. The complete run therefore took 23.2 minutes and produced nine files. Those numbers describe one difficult input, not how long every course's notes will take.

The episodes targeted 10-20 minutes, but one section with no internal headings became an episode of about 62 minutes. The result was not nine uniformly short recordings. It also did not establish whether listening would help me understand or retain the material; that needs listening and content review, beyond generating files.

Regeneration works at the source-file level: the saved state uses a fingerprint of the whole note. Editing any part regenerates all its episodes, while unchanged source files can be skipped.

**Update, October 16, 2026:** the current code can divide oversized sections at paragraph boundaries, following an October 10 fix. One indivisible paragraph can still exceed the target, and a new listening check is needed to assess the changed output. The saved narration text provides a way to inspect formula rewrites before relying on the audio. The [current project page](/projects/academic-hub/audio_generator/) covers output locations, textbook behavior, and the remaining limits.
