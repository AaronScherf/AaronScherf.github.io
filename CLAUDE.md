# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

**This repository is public** (it's the source for a GitHub Pages site, deployed via `.github/workflows/deploy.yml`). Never commit secrets, API keys, tokens, credentials, or other sensitive data anywhere in this repo — including in this file, in content, in config, or in commit messages. If a task seems to require a secret (e.g. an API integration), stop and ask how it should be supplied (GitHub Actions secrets, environment variables excluded via `.gitignore`, etc.) rather than hardcoding it.

## What this is

Aaron Scherf's personal/academic portfolio site (aaronscherf.github.io), built on the **HugoBlox "Academic CV"** template kit. Content is Markdown; the theme itself (layouts, blocks, CSS) is **not vendored in this repo** — it's pulled in at build time via Hugo Modules declared in `go.mod` / `config/_default/module.yaml` (`github.com/HugoBlox/kit/modules/blox`, `.../slides`, `.../integrations/netlify`). This repo only contains: content, config, a couple of custom overrides in `layouts/`, and `assets/media`.

## Commands

Requires **Hugo Extended** installed locally (not managed by npm/pnpm) — e.g. `scoop install hugo-extended` on Windows. Package manager is **pnpm** (pinned via `packageManager` in `package.json`); a stray `package-lock.json` also exists in the repo but pnpm is what CI and the devcontainer use.

```bash
pnpm install              # install JS deps (Tailwind CLI, pagefind, preact)
pnpm run dev              # hugo server --disableFastRender (local preview at :1313)
hugo server                # also works directly, once deps are installed
pnpm run build             # hugo --minify && pnpm run pagefind
pnpm run pagefind          # rebuild the pagefind search index over ./public only
```

There is no test suite or linter in this repo. Verify changes by running `pnpm run dev` and checking the page in a browser, and/or `pnpm run build` to confirm the production build succeeds.

## CI/deploy has two separate, drifting build paths

- `.github/workflows/build.yml` — runs on PRs. Uses **pnpm**, reads the Hugo version dynamically from `hugoblox.yaml` (`build.hugo_version`, currently `0.163.3`), falling back to `0.161.1` if unset.
- `.github/workflows/deploy.yml` — runs on push to `main`, actually publishes to GitHub Pages. Uses **npm** (not pnpm) and has the Hugo version **hardcoded** (`0.163.3`) independently of `hugoblox.yaml`.

These two files can silently drift (see commit `79931de "Pin CI Hugo version to fix broken TailwindCSS build"`, which had to patch `deploy.yml` specifically). **If you bump the Hugo version, update both `hugoblox.yaml` and `deploy.yml`.**

`netlify.toml` also exists (pnpm-based build) but `hugoblox.yaml` sets `deploy.host: github-pages`, so GitHub Actions is the live deploy path — treat the Netlify config as currently unused/vestigial unless told otherwise.

## Content model

Content lives under `content/<section>/`, each section following Hugo page-bundle conventions (a folder per item with `index.md` + any local assets like `cite.bib`, `featured.jpg`):

- `authors/me/` — the single author profile (bio, social links, skills) referenced by `username: me` throughout `params.yaml` and homepage blocks.
- `blog/`, `projects/`, `publications/{journal-article,conference-paper,preprint}/`, `events/`, `slides/`, `courses/` — one folder per content type.
- `experience.md` — resume experience entries, rendered via the `resume-experience` block.

The **homepage** (`content/_index.md`) is a single `type: landing` page built from an ordered list of `sections:` (blocks) — e.g. `resume-biography-3`, `resume-experience`, `resume-skills`, `resume-awards`, `resume-languages`, and `collection` blocks (used for the Blog feed).

**Placeholder sections, temporarily disabled**: the Papers, Talks, News, and Courses sections are commented out in both `content/_index.md` (`# TODO: re-enable once populated with real content`) and `config/_default/menus.yaml`, not deleted. They still had template placeholder text, not Aaron's real content, so they were hidden rather than published half-finished. The intent is to re-enable them later once each is filled in with real content — don't delete these blocks, and don't uncomment one on your own judgment call. When asked to bring a section back (or to fill it in), you'll generally need to: (1) write the real content, (2) uncomment its block in `content/_index.md`, and (3) uncomment the matching nav entry in `menus.yaml` (linking to `/#<id>`) — see `bf0bb11` and `c4eac26`, which did steps 2–3 together for these exact sections.

## Config

`config/_default/` holds `hugo.yaml` (core Hugo settings), `params.yaml` (site/theme params, ~290 lines), `menus.yaml` (nav), `languages.yaml`, `module.yaml` (Hugo Modules imports/mounts). `hugoblox.yaml` at the repo root is HugoBlox-specific metadata: template id, deploy host, and the pinned Hugo version CI builds against.

## Publications auto-import

`.github/workflows/import-publications.yml` watches for a `publications.bib` file at the repo root and, on push, runs the `academic` CLI to convert it into `content/publications/*/index.md` pages via an auto-generated PR. No `publications.bib` currently exists at the repo root, so this workflow is dormant — publication pages are currently hand-authored.
