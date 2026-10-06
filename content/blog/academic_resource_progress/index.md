---
title: Converting Academic Resources to Markdown
summary: "A progress update on turning textbooks and mixed-format class documents into searchable text, while checking where automatic conversion still loses information."
date: 2026-08-25
authors:
  - me
tags:
  - Academic Hub
  - Python
image:
  caption: 'Academic books and notes being converted into searchable text'
  image_suggestion: "Flow showing academic PDFs becoming searchable text, with separate paths for structured books and handwritten notes."
---

The [Academic Hub conversion tools](/projects/academic-hub/marker_conversion/) turn books and class documents into text that can be searched alongside my notes. Textbooks and handwritten or mixed-format documents need different approaches, so the project now has a tool for each.

<!--more-->

For textbooks, the converter now uses chapter boundaries where possible and records printed page numbers as well as PDF pages. In a four-book check, it avoided duplicate section markers and recovered printed page numbers on 96–98% of pages. A separate pass added descriptions to 764 of 793 candidate figures across five books, skipping the ones judged decorative.

Shorter documents such as exams and handwritten notes need a different path. A GPU-free tool checks whether ordinary text extraction is sufficient and sends only harder pages for more involved transcription. The work also uncovered problems that a plain text dump can hide: dropped spaces and lost superscripts. One square-root recognition error remains an open example of why extracted text still needs review.

The project is making course materials easier to search, but automatic conversion is not the same as a verified transcription. The [project page](/projects/academic-hub/marker_conversion/) has the validation details, known limits, and ongoing improvements.
