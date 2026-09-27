# Website agent routing

This is the single source of truth for roles and escalation in this repository.
Agent entry files and the bug procedure link here rather than repeating roles.

## Roles and escalation

- Gemini in Antigravity is the default website content manager: review source
  project material and documentation, write/revise project pages and blog posts,
  make ordinary editorial choices, preview pages, and check builds.
- Codex handles routine code/build defects, dependencies, CI maintenance, and
  Git mechanics when expected behavior is clear.
- Claude handles architecture, code/security review, layout/theme decisions,
  navigation or placeholder-section activation, and substantive configuration
  tradeoffs. Unclear expected behavior or reviewer ownership goes to Claude.

Normal prose, titles, structure within an existing page, and frontmatter that
follows existing conventions do not need architectural escalation. These are
defaults; the user's explicit assignment takes precedence.

Gemini gathers evidence for failures using [BUG_HANDOFF.md](BUG_HANDOFF.md).
Reviewers follow its reviewer responsibilities; a suspected cause is not proof.
Use [CLAUDE.md](../CLAUDE.md) for project commands and content conventions.

## Workspace ownership and source material

Use one writer per dedicated task branch/worktree of THIS repository, with
the IDE rooted there. The outer monorepo's worktree does not isolate this repo.
Use gemini/<task>, codex/<task>, or claude/<task> branches as appropriate.

Before writing/staging, verify git rev-parse --show-toplevel, the current
branch, and git status --short. Stop writes on a path/ownership mismatch.
Stage explicit task paths; never git add ., git add -A, or git commit -a.
Preserve unrelated changes. Do not reset or force-clean another session's work.

Source project repositories can be read as reference material. Record relevant
revisions and distinguish unfinished work from shipped results. Keep website
writes inside the owned website worktree; do not edit source projects as part
of content gathering.

One designated integrator combines completed branches sequentially and checks
the combined result. Remove worktrees only after ownership is released and
needed untracked/ignored artifacts are preserved. Never force removal.

These local rules apply to standalone clones; no outer-workspace document is
required to use this website workflow.

## Publication

Drafting/revising does not itself authorize publication. Preserve existing
publication status; keep new posts as drafts until publication is requested.
Pushes to main deploy via GitHub Actions. Publish only within the user's
authorization, including authorization already provided. Do not expose secrets
or private source material.
