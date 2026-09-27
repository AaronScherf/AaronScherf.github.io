# Website result checks and bug handoff

This is an agent procedure, not an automated validator. Apply it to content
edits, local previews/builds, and CI results. A successful build does not prove
that a page is correct. Roles and escalation are defined only in
[AGENT_ROUTING.md](AGENT_ROUTING.md#roles-and-escalation).

## Check the result

Establish expected behavior from the request and existing site conventions.
Check command status, output freshness, and the actual page: content,
frontmatter, links, images, layout, and requested rendering behavior. For a CI
failure, inspect the failing job/step. Record anything not checked.

Create a report when a command fails, the result differs from expectations,
or the user says it is wrong, even if the build passed. A complaint establishes
a mismatch, not a specific code defect. Editorial preferences can still be
revised normally; record the mismatch without calling it a confirmed bug.

## Preserve and investigate

1. Flag the mismatch and pause dependent publication. Preserve the failing
   page, build output, or screenshot before changing or regenerating it.
2. Record expected versus actual behavior and the user's correction. Do not
   silently repair evidence or declare success after an unexplained retry.
3. Reproduce safely in the owned worktree using the relevant page or build.
   Do not deploy to gather evidence. If not reproducible, record the limitation.
   Capture actual logs and browser observations; never invent a root cause.
4. Write the local report below, separating facts, hypotheses, and open questions.
   Give the user its absolute path, proposed reviewer using the routing doc,
   and a ready-to-use handoff prompt. Do not claim a reviewer has received or
   reviewed it without evidence. Continue independent work.

## Report storage

Resolve the owned repository root with `git rev-parse --show-toplevel`.
Write reports below that absolute root, regardless of the current directory:
`<repo-root>/.agent-reports/bugs/<YYYYMMDD-HHMMSS>-<short-slug>/`.
Use a unique directory; do not overwrite a report. Before saving any evidence,
run `git -C <repo-root> check-ignore -v -- <absolute-report-path>` for the
intended report and attachment paths and require a matching rule. If any path
is not ignored, stop saving evidence there until the repository's rule is fixed.
The rule must be in the actual repository receiving the files; an outer repo's
.gitignore does not protect a child repository. Existing tracked files are not
protected by adding an ignore rule. Never force-add reports.

If the original checkout is shared/read-only, create an owned worktree for
the report and identify the original checkout separately. Never include secrets.
Minimize personal/private data; use redacted excerpts or local references.
Do not stage reports or publish issues automatically. Share only within the
user's authorization and preserve needed reports before deleting a worktree.
Gitignore provides neither backup nor access control.

## Report template

Create report.md with:

- Title, date, reporter, proposed reviewer, and status (reported / reproduced /
  awaiting review / fixed-awaiting-validation / verified / unresolved).
- User request/correction, expected versus actual behavior, impact.
- Original repository/worktree, branch, commit, relevant dirty files and
  safely retained diff; checkout/revision needed to reproduce.
- Affected content bundle/source path, page URL/route, frontmatter and asset
  references relevant to the failure. Identify draft/publication status.
- Exact command and working directory; Hugo Extended version, Node and package
  manager versions, relevant lockfile/module/config revisions for build issues.
- For rendering issues: browser/version, viewport, local preview versus
  deployed page, screenshot and console/network evidence where relevant.
- For CI issues: workflow file, run URL/ID, job/step, commit, and relevant
  redacted logs. Distinguish PR build from deployment workflow behavior.
- Minimal reproduction, attempts, observed repeatability, missing evidence.
- Evidence paths: failing HTML/page, screenshot, logs/exit status, link checks,
  or supporting source material. Label redactions.
- Initial investigation map: content, assets, layout overrides, Hugo modules,
  configuration, or workflow files examined. This is not a review boundary.
- Observations versus suspected causes; consider stale builds/assets, draft
  settings, URL configuration, environment drift, and unclear requirements.
- Acceptance criteria and a proposed focused regression/render/build check.
- Handoff prompt: "Review <absolute report path> against the relevant full
  website codebase at <checkout/revision>. Reproduce the mismatch, trace the
  content-to-render/build path and dependencies beyond the initial file list,
  distinguish code/configuration/content issues, and fix within your assigned
  role. Validate the recorded acceptance criteria."
- Reviewer findings, fix commit, validation results, and remaining limitations
  (pending until actually reviewed).

Include only relevant diagnostic fields; mark unavailable evidence honestly.

## Reviewer responsibilities

Use [the routing rules](AGENT_ROUTING.md#roles-and-escalation) to assign or
escalate the case. Independently inspect the relevant full website codebase:
content/frontmatter, assets, layouts, Hugo modules, configuration, and build/
deployment workflows as applicable. Do not accept the proposed cause as fact
or patch only the visible symptom; avoid unrelated whole-tree dumps.

After a fix, repeat the original reproduction and relevant build/render checks.
Have Gemini recheck the original user workflow. Subjective correctness may need
user confirmation. Close only once acceptance criteria are checked; otherwise
retain awaiting-validation/unresolved status and name the missing check.
