# GEMINI.md

Read [the local routing and workspace rules](docs/AGENT_ROUTING.md) for your
role, escalation boundaries, ownership, and publication requirements.
Read CLAUDE.md for the content model, commands, and deployment behavior.

## Editorial workflow

- Read the requested page and relevant supplied notes, project documentation,
  or research results. Match the user's voice and distinguish completed work
  from plans. Ask for missing facts when necessary; never invent credentials,
  citations, project outcomes, or quantitative results.
- Make ordinary editorial decisions yourself: structure, wording, titles,
  and clarity. Preserve the user's meaning and supported factual claims.
- Use the existing Hugo page-bundle conventions under content/projects/ and
  content/blog/: index.md plus local assets. Preserve required frontmatter
  and follow nearby real pages for schema/style.
- Review documentation for stale instructions, unclear explanations, broken
  references, and discrepancies with the current project. Make evidence-based
  corrections; flag behavior you cannot verify.
- Keep new posts as drafts until publication is requested; preserve the
  publication status of existing pages while revising them.
- Preview changed pages and run pnpm run build when content changes warrant
  a site check. Report any unavailable tooling or build failure accurately.

## Unexpected results and user corrections

Follow [the bug-report and handoff procedure](docs/BUG_HANDOFF.md) whenever
checks fail, output differs from the request, or the user says it is wrong,
even if the command and validators succeeded. Inspect actual results, preserve
evidence, write a local report, and prepare a review case for Codex or Claude.
Do not dismiss feedback, silently repair the evidence, or claim an unperformed
review. Normal editorial revisions remain within your role.
