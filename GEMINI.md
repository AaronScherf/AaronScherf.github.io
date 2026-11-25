# GEMINI.md

Read [the local routing and workspace rules](docs/AGENT_ROUTING.md) for your
role, escalation boundaries, ownership, and publication requirements.
Read CLAUDE.md for the content model, commands, and deployment behavior.

## Editorial workflow

Before drafting or revising a blog post, read [the blog post standards](docs/editorial/blog-post-standards.md).

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

## Citing literature

Any page that cites a paper, whether it gives a DOI, a reference list or an author-year claim, follows the monorepo's checker rule. This repo has no landing gate, so the check is part of finishing the draft:
- Take identifiers and bibliographic details from a registry lookup or the supplied source file, never from memory.
- Give every citation the work's title. Find the work in a registry by title and authors, then take its DOI from that record; never fill in a title by reading a DOI's record. A name, year and DOI alone do not show which work you meant.
- Before reporting a draft as ready, run `python -m tools.reference_checker <path to index.md> --format markdown` from the monorepo's `ai-sandbox/academic-rag-model/`.
- Every DOI must come back CONFIRMED (or DESCRIBED for a descriptive link). AUTHOR_YEAR is not enough on a page: it means the citation has no title, so add the title of the work you mean. Fix WRONG_WORK, NOT_FOUND and TITLE_WRONG rows by finding the work you meant, not by copying the DOI's registered title.
- Report anything else (REVIEW, PLAUSIBLE, UNRESOLVED) to the user, and flag it for Claude's review page. Do not publish with an open row.
- Do not mark citations as verified yourself. A matched DOI does not show that the paper supports the sentence; quote findings only from a paper you have read.

## Unexpected results and user corrections

Follow [the bug-report and handoff procedure](docs/BUG_HANDOFF.md) whenever
checks fail, output differs from the request, or the user says it is wrong,
even if the command and validators succeeded. Inspect actual results, preserve
evidence, write a local report, and prepare a review case for Codex or Claude.
Do not dismiss feedback, silently repair the evidence, or claim an unperformed
review. Normal editorial revisions remain within your role.
