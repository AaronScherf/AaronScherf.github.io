---
title: Multi-Agent Development Workflow
date: 2026-09-27
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/ai-sandbox-master/blob/main/docs/AGENT_ROUTING.md
tags:
  - LLM / RAG
  - Developer Tools
---

Three AI coding agents — Claude Code, Gemini (Antigravity), and OpenAI Codex — work the same monorepo behind Academic Hub and the AI Research Assistant. Rather than let task assignment be ad hoc, or let all three edit the same checkout at once, this project is the routing convention and git-isolation procedure that make three agents on one codebase a deliberate workflow instead of a liability.

<!--more-->

The problem isn't capability, it's coordination. Each of the three tools is good at something different, and none of them share memory: a Claude Code session in this workspace carries cross-session context forward, while Gemini and Codex start cold every time. Left unmanaged, that difference doesn't matter — whichever tool is open just does the task, regardless of whether it's the right one for the job, and if two sessions happen to touch the same working directory at once, one can silently overwrite the other's files or git state.

The fix has two layers. The first is a routing convention, written once in `docs/AGENT_ROUTING.md` and linked from a dedicated entry-point file per agent (`CLAUDE.md`, `GEMINI.md`, `AGENTS.md`) rather than copied into all three — a deliberate choice made after watching a *different* piece of shared config in this same workspace drift silently once each device started stamping its own version over it. Routing goes by task shape, not tool preference: Claude takes judgment calls, architecture, and anything that depends on prior decisions; Gemini takes large-context reads that don't require picking a direction — summarizing dozens of files or a long status doc, then reporting back rather than deciding; Codex takes routine, mechanical, well-specified work like git mechanics, test runs, and boilerplate. Escalation runs both ways: a routine agent that hits a real design decision mid-task stops and flags it up rather than guessing, and Claude hands large mechanical or read-heavy work down instead of burning its own session budget on it.

The second layer is git isolation, added after the routing convention alone proved to only answer *who* does a task, not how three agents avoid clobbering each other while doing it. The rule is one branch and one Git worktree per writing task, exactly one writer per worktree, with a per-agent branch-naming convention (`claude/<task>`, `gemini/<task>`, `codex/<task>`) and a single designated integrator responsible for merging finished work back into main. Worktrees isolate checked-out files, HEAD, and the staging area, but git objects, refs, and remotes stay shared — so the procedure is explicit about what it doesn't solve: it prevents accidental working-file overwrites, not merge conflicts or genuinely incompatible changes, and it depends on every session actually reading and following it rather than assuming automatic discovery.

Both pieces get revisited as gaps surface in practice rather than designed exhaustively up front: whether a repo-root context file is even discovered when a session launches from inside a subproject directory is still an open, only partly-confirmed question, and there's no enforcement mechanism beyond each session self-reporting when it should escalate or hand off. For a manual, single-user workflow, that's judged to be the right amount of process — a standalone dispatch layer was considered and deliberately deferred as premature.
