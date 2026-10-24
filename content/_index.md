---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2022-10-24
type: landing

# Hide the generic "share this page" tray (X/Facebook/WhatsApp/etc.) site-wide
# -- the author bio already surfaces the real social links (Bluesky, GitHub,
# etc.), so this redundant, unrelated widget is just noise everywhere it
# appears. Cascades from the site root to every page unless a page's own
# frontmatter sets `share: true` to opt back in.
cascade:
  share: false

sections:
  - block: resume-biography
    content:
      username: me
      button:
        text: Download CV
        url: uploads/resume.pdf
    design:
      background:
        gradient_mesh:
          enable: true
      avatar:
        size: medium
        shape: circle
  - block: markdown
    content:
      title: 'How I Can Help'
      subtitle: ''
      text: |-
        I am available for consulting and applied research projects that need both technical analysis and an understanding of how decisions get made in practice. My work with USAID and in research has prepared me to help with:

        - **Program design and evaluation:** Turn a broad goal into a workable plan for measuring results, then make sense of the evidence as conditions change.
        - **Geospatial and data analysis:** Combine satellite, field, and administrative data to answer questions about places where information is incomplete.
        - **Research and decision tools:** Build practical workflows that make sources easier to find, check, and use.

        If one of these fits a problem you are working on, [email me](mailto:theaaronscherf@gmail.com) to discuss it. You can also [download my CV](/uploads/resume.pdf) and explore the projects below.
    design:
      columns: '1'
  - block: collection
    id: projects
    content:
      title: Selected Projects
      subtitle: ''
      text: 'These projects show how I approach work across development research and practical software: from testing whether satellite data can help predict wheat yields to building tools that keep research and study materials connected to their sources.'
      page_type: projects
      count: 6
      filters:
        folders:
          - projects
    design:
      view: article-grid
      fill_image: false
      columns: 2
      show_date: false
      show_read_time: false
      show_read_more: false
  - block: markdown
    content:
      title: My Research
      subtitle: ''
      text: |-
        My research asks when detailed information about a place can change a decision, and when it only creates the appearance of certainty. I am especially interested in how climate stress, conflict, and disasters interact, and how satellite observations and statistical models can be checked against evidence from the ground.

        In my [wheat-yield project](/projects/wheat_yield_prediction/), I compared satellite measurements with field records to test how well different models predicted crop performance in new environments. That question—what a model can tell us when local data are scarce, and what it cannot—also shapes the work I want to pursue in sustainable development.
    design:
      columns: '1'
  - block: resume-experience
    id: experience
    content:
      username: me
    design:
      # Hugo date format
      date_format: 'January 2006'
      # Education or Experience section first?
      is_education_first: false
  - block: resume-skills
    content:
      title: Skills
      username: me
  - block: resume-awards
    content:
      title: Awards
      username: me
  - block: resume-languages
    content:
      title: Languages
      username: me
  # TODO: re-enable once populated with real content (currently template placeholders)
  # - block: collection
  #   id: papers
  #   content:
  #     title: Featured Publications
  #     filters:
  #       folders:
  #         - publications
  #       featured_only: true
  #   design:
  #     view: article-grid
  #     columns: 2
  # - block: collection
  #   content:
  #     title: Recent Publications
  #     text: ''
  #     filters:
  #       folders:
  #         - publications
  #       exclude_featured: false
  #   design:
  #     view: citation
  # - block: collection
  #   id: talks
  #   content:
  #     title: Recent & Upcoming Talks
  #     filters:
  #       folders:
  #         - events
  #   design:
  #     view: card
  - block: collection
    id: blog
    content:
      title: Blog
      subtitle: ''
      text: ''
      # Page type to display. E.g. post, talk, publication...
      page_type: blog
      # Choose how many pages you would like to display (0 = all pages)
      count: 10
      # Filter on criteria
      filters:
        author: ''
        category: ''
        tag: ''
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ''
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: article-grid
      fill_image: false
      columns: 2
      show_date: false
      show_read_time: false
      show_read_more: false
      # Reduce spacing
      spacing:
        padding: [0, 0, 0, 0]
  - block: cta-card
    demo: true # Only display this section in the HugoBlox Kit demo site
    content:
      title: 👉 Build your own academic website like this
      text: |-
        This site is generated by HugoBlox Kit - the FREE, Hugo-based open source website builder trusted by 250,000+ academics like you.

        <a class="github-button" href="https://github.com/HugoBlox/kit" data-color-scheme="no-preference: light; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star HugoBlox/kit on GitHub">Star</a>

        Easily build anything with blocks - no-code required!

        From landing pages, second brains, and courses to academic resumés, conferences, and tech blogs.
      button:
        text: Get Started
        url: https://hugoblox.com/templates/
    design:
      card:
        # Card background color (CSS class)
        css_class: 'bg-gradient-to-br from-primary-500 via-primary-600 to-secondary-600 text-white shadow-2xl'
        css_style: ''
---
