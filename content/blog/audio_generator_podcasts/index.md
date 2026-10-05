---
title: "Turning Dense Math Notes into Commute Podcasts: How I Built an Offline/Cloud Audio Pipeline"
summary: "Standard text-to-speech engines choke on raw LaTeX. How I built an automated audio generation pipeline that classifies equation density, uses Gemini to translate formulas into natural spoken prose, greedily batches sections into 10–20 minute MP3 episodes, and synthesizes speech offline via concurrent Piper workers."
date: 2026-10-01
authors:
  - me
tags:
  - Academic Hub
  - Python
  - Audio / TTS
  - LLM / RAG
image:
  caption: 'Audio Generator pipeline from LaTeX density classification and parallel Gemini conversational translation to multi-worker Piper TTS episode batching'
  image_suggestion: "Technical architecture and data-flow diagram for an audio generation system: showing Markdown notes passing through LaTeX formula density classification, parallel thread-pool dispatch to Gemini for conversational translation, section-aware greedy batching (calibrated at 969 chars/min), and offline synthesis via 3 concurrent Piper TTS workers into MP3 podcast episodes."
---

Graduate school generates an overwhelming volume of reading. Between textbook chapters, professor lecture transcripts, and teaching assistant review notes, there are always dozens of pages left unread. 

Naturally, you look for ways to reclaim dead time: walking the dog, commuting on the subway, washing dishes, or running on the treadmill. But if you try to throw technical academic notes into standard text-to-speech (TTS) apps (like Speechify or Voice Dream), the experience collapses the moment it hits an equation.

<!--more-->

*Figure: Audio Generator pipeline from LaTeX density classification and parallel Gemini conversational translation to multi-worker Piper TTS episode batching.*

A standard screen reader encounters $\frac{\partial^2 f}{\partial x_i \partial x_j}$ and reads it out verbatim: *"backslash frac open-curly-brace backslash partial squared f close-curly-brace open-curly-brace backslash partial x sub i backslash partial x sub j close-curly-brace."* Within two minutes, you are listening to unpronounceable syntax soup.

To solve this, I built the **[Audio Generator](/projects/academic-hub/audio_generator/)** — a hybrid offline/cloud audio pipeline that turns dense Markdown notes and converted textbooks into structured, highly listenable 10–20 minute podcast episodes.

Here is the engineering journey behind how it works, the concurrency mistakes I made along the way, and the benchmarks that took translation time from six hours down to under four minutes.

---

### 1. The Core Obstacle: Translating LaTeX into Spoken English

The primary challenge of technical audio is not speech synthesis — modern open-source TTS voices sound remarkably natural. The hard problem is **translating symbolic mathematics into spoken conversational prose**.

When a mathematician reads $\lim_{n \to \infty} \sum_{k=1}^n \frac{1}{k^2} = \frac{\pi^2}{6}$ aloud, they don't read the symbols; they say: *"the limit as n goes to infinity of the sum of one over k squared equals pi squared over six."*

#### Attempt 1: Regex Replacement (Unlistenable)
My first instinct was simple: write regular expressions to strip LaTeX delimiters (`$...$`, `$$...$$`) and wrap equations in descriptive tags. This failed immediately. Real mathematical notes contain nested superscripts, matrices, piecewise functions, and tensor products that no regex can reliably untangle. The output was still filled with literal command syntax.

#### Attempt 2: Local Open-Source LLMs (The 6-Hour Wall)
Next, I routed equation translation to a local open-weight model (`qwen2-math:7b` running via Ollama). The mathematical quality was genuinely impressive — it parsed complex proofs and described the algebraic intuition accurately.

The problem was throughput. Testing the model end-to-end against a real 121,637-character lecture notes file took **roughly six hours** on local hardware. For a student with multiple courses and hundreds of thousands of words of notes, a six-hour queue per document is completely impractical.

#### Attempt 3: Density-Tiered Classification & Concurrent Cloud API
To achieve real-time speed without paying exorbitant cloud costs, I built a **density-tiered classification router**:
1. **No-Math Chunks**: Chunks containing pure text make zero API calls, passing straight to speech synthesis for free.
2. **Sparse Notation**: Chunks with occasional single variables or basic terms route to a cheap, lightweight model (`gemini-3.1-flash-lite`).
3. **Dense Equations**: Chunks with multi-line derivations or complex matrices route to a stronger model with explicit prompts instructing it to narrate the intuition rather than spelling out characters.

Because hosted cloud APIs can serve requests concurrently (unlike a single local model that serializes execution), chunks are dispatched through a parallel thread pool. 

---

### 2. The 3-Hour Monolith Problem and Greedy Episode Batching

Once parallel translation worked, the pipeline generated its first complete audio file for the 121,637-character notes document. 

It worked, but the result was **a single MP3 file that was 3 hours and 22 minutes long**.

A three-hour audio file is useless for everyday listening. You cannot easily navigate topics on your phone, you lose your place if your podcast app resets, and the cognitive fatigue of listening to a single continuous monologue is exhausting.

To turn this into a true podcast format, I designed a **section-aware greedy batching algorithm**:

1. **Header-Based Splitting**: The note is partitioned at every primary Markdown heading (`#`, `##`), ensuring topical boundaries are preserved.
2. **Empirical Speech Calibration**: Rather than guessing words-per-minute, I measured real output from the Piper speech engine. The calibration settled at **969 characters of cleaned text per minute of audio**.
3. **Greedy Bin-Packing**: The pipeline groups consecutive sections into target windows of **10 to 20 minutes**. If adding another section would push the episode over 20 minutes, it closes the episode, writes an ID3 tag, and starts a fresh file.

#### The Concurrency Trap
The first version of this grouping had a subtle architectural flaw: it looped over sections sequentially, only parallelizing chunks within each individual section. This artificially throttled network throughput. 

By refactoring the pipeline to flatten every section's chunks into a single global dispatch pool, translation time for a 74-section document plummeted from **13 minutes down to 3.8 minutes**.

---

### 3. Fast, Offline Speech Synthesis via Multi-Worker Piper

Once the text is translated and grouped into episodes, speech synthesis happens entirely **offline on CPU**:
- **Piper TTS**: A fast, local neural text-to-speech engine optimized for consumer hardware.
- **Multi-Worker Concurrency**: On a standard multi-core laptop, synthesis is distributed across three concurrent worker processes (`multiprocessing`). 

Testing across the same 121,637-character file demonstrated a near-linear **2.9x speedup** over sequential rendering:

| Processing Stage | Single-Threaded / Local LLM | Parallel Cloud + Multi-Worker Piper | Improvement |
| :--- | :--- | :--- | :--- |
| **Formula Translation** | ~360 min (`qwen2-math:7b`) | 3.8 min (Parallel Gemini) | **95x faster** |
| **Audio Synthesis** | 56.2 min (1 worker) | 19.4 min (3 workers) | **2.9x faster** |
| **Total End-to-End Time** | **> 6.9 hours** | **23.2 minutes** | **~18x speedup** |
| **Output Deliverable** | 1 monolithic 3h 22m file | **9 clean, 15-minute MP3 episodes** | Commute-ready |

The total cloud cost for translating the entire document was less than two cents.

---

### 4. Honest Trade-Offs and Edge Cases

A production engineering pipeline is only as good as its acknowledged limitations. In practice, two real-world edge cases surfaced:

1. **Header-less Monoliths**: Because the greedy batcher strictly respects section headers to avoid cutting an argument in half, a single 711-line section with no intermediate subheadings generated a 62-minute episode. Rather than adding arbitrary paragraph splits that could cut off a proof mid-derivation, I kept the boundary intact.
2. **Metadata Cleaning**: Notes synthesized from video lectures often contain per-sentence timestamp links (such as `[12:34]`). The audio pipeline includes a cleaning pass that strips these visual citations before narration, ensuring the listener isn't subjected to continuous timestamp announcements.
3. **Content Hashing**: Every generated MP3 is keyed to a SHA-256 hash of its source Markdown file. If I edit a single typo in section 3, a rebuild only reconverts that specific episode, leaving the other eight untouched.

---

### Why This Matters

This project illustrates the power of **hybrid system design**:
- Don't force local hardware to do what elastic cloud APIs do best (parallel semantic translation).
- Don't pay cloud subscriptions for what local hardware can do for free (neural audio synthesis).
- Always design data outputs around the human user’s physical habits and context.

By transforming dense, equation-heavy course notes into cleanly segmented audio episodes, I can reinforce difficult graduate concepts while commuting or walking across campus — turning passive downtime into productive, screen-free learning.
