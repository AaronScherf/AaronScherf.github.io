# Live site readiness audit — 2026-10-19

Source deployed when checked: `2bb05d936d8fea7d75ed27b89067e4dd9635f9b7`. This is a live HTTP and source review, not a visual test in a browser at multiple screen sizes.

## Confirmed working

- The GitHub Pages deployment completed successfully. All 82 sitemap URLs returned HTTP 200, including all 15 published blog articles and the five retrospective milestone posts.
- All 88 distinct same-site links found across sitemap pages returned HTTP 200. All 122 image URLs in those pages returned HTTP 200. Homepage CSS and script assets returned HTTP 200.
- No published page exposed an `[[Insert Image: ...]]` brief, `Lorem ipsum`, or a retrospective *draft* note. The five milestone posts have substantive opening paragraphs, historically scoped claims, and links to the underlying project pages or dated records.
- Of 16 distinct external links found in blog pages, 14 returned HTTP 200. LinkedIn blocked automated checking with HTTP 999 and Medium with HTTP 403; those responses do not establish that the links are broken for a visitor.

## Functional issue fixed on this branch, pending deployment

The live homepage search loads `/pagefind/pagefind.js`, which currently returns HTTP 404. The deployment workflow runs Hugo but omits the Pagefind index command that the PR build already runs. This branch adds `npm run pagefind` after Hugo and before artifact upload. Search will remain broken on the live site until this branch is merged and deployed, then its live behavior should be checked again.

The live search modal also falls back to visible template suggestions, “Search term 1” and “Search term 2”. This branch supplies three real suggested topics: handwritten notes, study guides, and research papers.

Local verification: Hugo Extended 0.163.3 built 126 pages; `npm run pagefind` indexed 43 searchable pages and generated `public/pagefind/pagefind.js`; the deployment workflow YAML parses.

## Accessibility issue fixed on this branch, pending deployment

Eight published blog articles and the AI Research Assistant overview lacked alt text on their featured images. This branch adds concise descriptions to those nine page bundles. The nine images themselves are unchanged. Live image accessibility should be rechecked after deployment.

Local verification: all nine generated article pages contain the new alt text on their featured-image element.

## Image credibility and presentation still need editorial work

The newer five milestone images and the `academic_hub` and `audio_generator_podcasts` blog images passed this review. The following older images remain live and should be corrected before calling the site polished. Before replacing a `featured.jpg`, preserve it as `docs/editorial/image-candidates/<slug>/original-featured.jpg`, consistent with the existing image archive. Use the established dark navy, teal, and muted violet style with fewer labels and clear mobile-scale composition. These are illustrations, not screenshots or verified run records.

**High priority — misleading visible details:**

1. `pedagogical_rag_hints`: The diagram displays a fabricated proof and garbled mathematical text. Replace it with one question branching into a hint and a separate check of the student's attempt; show no proof steps, scores, or fabricated interface.
2. `textbook_conversion_automation`: The diagram says VM resizing and on-call alerting are automatic. The post says a person or coding agent follows the recovery procedure. Show duplicate detection, reuse/review, and a supervised retry or larger-machine decision, with no automatic scaling or on-call service.
3. `indexer_and_rag_progress`: The fake terminal answer includes garbled mathematics and specific-looking book/page citations that are not verified. Show course/document narrowing, passage retrieval, and a source-linked answer with generic source markers; no invented answer text or citations.
4. `site_management`: The fake terminal/browser screenshots contain filler copy and fabricated contact details. Show Markdown change, human review, GitHub Actions build, and published page as a simple editorial diagram; avoid realistic fake site content.
5. `ai-research-assistant-overview`: The image invents faculty names and depicts precise architecture (a five-tier download waterfall, federated vector collections, and knowledge packets) beyond what the page establishes. Show the three actual flows—paper discovery, article conversion, and research-note conversion—meeting the Source Indexer and searchable research collection.

**Next priority — legibility or claims to verify:**

6. `obsidian_excalidraw_notes`: Garbled equations crowd the image. Emphasize automatic SVG export on save, transcription into searchable text, and the ability to modify plugins for tablet controls; omit mathematical notation.
7. `academic_resource_progress`: The image has visibly malformed labels and depicts specific cloud infrastructure not explained in the post. Show textbook conversion with printed/PDF page tracking and figure descriptions beside tiered lecture-note transcription and notation repair.
8. `academic_journal_discovery`: The image is too dense for a thumbnail and names a detailed service waterfall. Verify every named source against the code, or simplify to OpenAlex candidates, local relevance scoring, owner review, available full-text download, manual-access queue, and conversion.
9. `academic_hub_infrastructure_cleanup`: The two-panel image is crowded at article width and includes implementation labels whose exactness should be checked. Show the documented notes-history reduction (about 217 MB to 35 MB), separation of heavy source files, and code grouped by function.

After replacements, inspect every visible word and arrow at full resolution and thumbnail size, write alt text for the final image, rebuild, and check the live page. The source text and internal link structure do not need a broad rewrite for this image follow-up.
