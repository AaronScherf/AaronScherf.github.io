---
title: Managing this site with HugoBlox and Claude
summary: A look at how this site is built on Hugo and HugoBlox, and how I use Claude Code as a hands-on collaborator to manage its content and layout.
date: 2026-08-19
authors:
  - me
tags:
  - Hugo Blox
  - Claude Code
---

This site runs on **Hugo**, a static site generator, using the open-source **HugoBlox** "Academic CV" template. Everything you're reading — my bio, experience, projects, and this post — is a plain Markdown file with a bit of YAML front matter controlling how it's displayed. There's no database and no CMS login; I edit files directly in the repository, and GitHub Actions rebuilds and redeploys the site automatically every time I push to `main`.

<!--more-->

Lately I've been doing a lot of that editing with **Claude Code**, working directly in the repository rather than through a hosted CMS. It reads the site's structure, makes the same kind of edits I would — adding a project page, hiding placeholder content, restructuring navigation, adjusting a grid layout — and hands off a normal git commit for me to review and push.

A few examples from recent sessions: consolidating the site from multiple pages into a single scrolling homepage with anchor-based navigation, adding new project entries — like [Marker PDF Conversion](/projects/academic-hub/marker_conversion/) and [RAG Analysis](/projects/academic-hub/rag_analysis/) — for tools I'm building as part of a larger effort I'm calling **Academic Hub**, and quietly retiring the template's placeholder content by marking it `draft: true` rather than deleting it outright — so it's still there if I ever want it back.

It's a fairly low-friction way to keep a personal site current: content lives in version control, changes are reviewable as diffs before they go live, and the parts of web development I don't want to hand-roll — layout, styling, deployment — stay handled by the template and CI pipeline underneath.
