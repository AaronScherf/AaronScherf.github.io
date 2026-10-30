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
        I am available for consulting and applied research projects that require advanced technical analysis and practical experience in international development. I can help with:

        - **Program design and evaluation:** Turn problem statements into actionable plans for implementing programs and measuring results in rapidly changing conditions.
        - **Geospatial data analysis:** Combine satellite, survey, and administrative data to answer questions about places where information is incomplete.
        - **Research and decision tools:** Build reproducible workflows that fuse diverse data sources to create actionable insights and intuitive visualizations.
        - **Literature reviews and gap analysis:** Conduct comprehensive reviews of existing development knowledge sources to identify gaps and inform projects.
        - **Development proposal writing:** Help organizations develop compelling proposals that propose novel solutions to international development challenges.
        - **Training & Skills Workshops:** Share my experience and expertise via in-person or online workshops, as well as personalized skills development coaching.

        If I can help with a problem you are working on, [email me](mailto:theaaronscherf@gmail.com) to discuss it. You can also [download my CV](/uploads/resume.pdf) and explore my [past projects](https://aaronscherf.github.io/#projects).
    design:
      columns: '1'
  - block: collection
    id: projects
    content:
      title: Selected Projects
      subtitle: ''
      text: 'My past projects cover diverse topics, from applied development research to tools that organize and explore information in novel formats.'
      page_type: projects
      count: 6
      sort_by: Weight
      order: desc
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
        My current research focuses on how communities prepare for and recover from overlapping climate disasters, armed conflict, and economic shocks. I am especially interested in whether social protection and disaster financing, such as index insurance and pre-crisis cash assistance, can protect livelihoods, reduce displacement, and improve long-term recovery. I want to examine how lessons from natural disaster response and resilience can be adapted for conflict settings, and how interventions impact communities differently in distinct contexts.

        This agenda builds on my experience combining satellite observations and experimental data to [compare crop-yield prediction models](/projects/wheat_yield_prediction/), applying advanced quantitative analysis and machine learning, and building reproducible tools for processing and organizing diverse datasets. I aim to combine methods from economics, climate science, machine learning and software development with my personal experience implementing development programs to better plan and evaluate humanitarian and social protection programs in rapidly changing and information scarce environments.
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
  # Hidden for now; the skills remain in data/authors/me.yaml.
  # - block: resume-skills
  #   content:
  #     title: Skills
  #     username: me
  # Hidden for now; the awards remain in data/authors/me.yaml.
  # - block: resume-awards
  #   content:
  #     title: Awards
  #     username: me
  # Hidden for now; the languages remain in data/authors/me.yaml.
  # - block: resume-languages
  #   content:
  #     title: Languages
  #     username: me
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
      button:
        text: Get Started
        url: https://hugoblox.com/templates/
    design:
      card:
        # Card background color (CSS class)
        css_class: 'bg-gradient-to-br from-primary-500 via-primary-600 to-secondary-600 text-white shadow-2xl'
        css_style: ''
---
