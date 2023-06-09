---
# Leave the homepage title empty to use the site title
title:
type: landing

sections:
  - block: about.biography
    id: about
    content:
      title: Biography
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: Shenghui-Gu
  - block: collection
    id: posts
    content:
      title: Posts
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        folders: [post]
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: compact
      columns: "2"
  - block: collection
    id: publications
    content:
      title: Publications
      filters:
        folders: [publication]
    design:
      view: citation
      columns: "2"
  - block: experience
    content:
      title: Experience
      # Date format for experience
      #   Refer to https://wowchemy.com/docs/customization/#date-format
      date_format: Jan 2006
      # Experiences.
      #   Add/remove as many `experience` items below as you like.
      #   Required fields are `title`, `company`, and `date_start`.
      #   Leave `date_end` empty if it's your current employer.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - title: Backend Development Engineer Intern
          company: Meituan, Basic Development Platform, System Monitoring Team
          company_url: "https://about.meituan.com"
          company_logo: meituan
          location: Shanghai, China
          date_start: "2022-07-11"
          date_end: "2023-06-05"
          description: |2-
            * Led a three-person team to develop a log data valuation system utilizing deep learning and explainable artificial intelligence technologies.
            * Validated the prototype on open-source datasets, providing the foundation for the team to save costs on log data storage and analysis.
            * Acquired knowledge in machine learning, deep learning, and explainable artificial intelligence.
            * Technical Skills: Python (PyTorch, NumPy, Pandas, Matplotlib, etc.), Linux tools, Git.
        - title: Backend Development Engineer Intern
          company: Meituan, Basic Development Platform, System Monitoring Team
          company_url: "https://about.meituan.com"
          company_logo: meituan
          location: Shanghai, China
          date_start: "2021-07-05"
          date_end: "2021-12-10"
          description: |2-
            * Led a three-person team to develop an anomaly root cause analysis system utilizing multiple monitoring data sources and deployed the system in a production environment.
            * Built anomaly root cause analysis capabilities from scratch for the team at the company.
            * Technical Skills: Java, TypeScript, HTML/CSS, Linux tools, Git.
        - title: Backend Development Engineer Intern
          company: Transwarp Information Technology (Shanghai) Co., Ltd., Infrastructure Department
          company_url: "https://transwarp.cn/en"
          company_logo: transwarp
          location: Shanghai, China
          date_start: "2018-01-11"
          date_end: "2019-07-12"
          description: |2-
            * Developed an AIOps platform including log analysis, JStack analysis, and operational knowledge base.
            * Provided support for adding, deleting, and modifying columns in database tables for a distributed columnar database.
            * Acquired knowledge of big data technologies, including distributed architecture and database principles.
            * Technical Skills: Scala, Java, TypeScript, JavaScript, HTML/CSS, Linux tools, Git.
        - title: DevOps Engineer Intern
          company: Shanghai Kaian Technology Co., Ltd.
          company_url: "https://www.madailicai.com"
          company_logo: madailicai
          location: Shanghai, China
          date_start: "2017-06-01"
          date_end: "2017-09-01"
          description: |2-
            * Maintained a continuous integration platform.
            * Acquired knowledge in DevOps, continuous integration/deployment.
    design:
      columns: "2"
  - block: features
    content:
      title: Skills
      items:
        - name: Python (PyTorch, NumPy, Pandas, Matplotlib, etc.)
          icon: python
          icon_pack: fab
        - name: Java (Scala)
          icon: java
          icon_pack: fab
        - name: JavaScript (TypeScript)
          icon: js
          icon_pack: fab
        - name: HTML/CSS
          icon: html5
          icon_pack: fab
        - name: SQL
          icon: database
          icon_pack: fas
        - name: Go
          icon: golang
          icon_pack: fab
        - name: Linux
          icon: linux
          icon_pack: fab
        - name: Shell (Bash/Zsh)
          icon: terminal
          icon_pack: fas
        - name: Git
          icon: git-alt
          icon_pack: fab
  - block: tag_cloud
    content:
      title: Popular Topics
    design:
      columns: "2"
  - block: contact
    id: contact
    content:
      title: Contact
      # Contact (add or remove contact options as necessary)
      email: shenghui.gu@smail.nju.edu.cn
      # phone: 888 888 88 88
      # appointment_url: "https://calendly.com"
      address:
        street: 50 Hankou Road, Gulou District
        city: Nanjing
        region: Jiangsu
        postcode: "210093"
        country: China
        country_code: CN
      directions: Feiyimin Building 6F
      office_hours:
        - "Workday 10:00 to 17:00"
      # contact_links:
      #   - icon: twitter
      #     icon_pack: fab
      #     name: DM Me
      #     link: "https://twitter.com/Twitter"
      #   - icon: skype
      #     icon_pack: fab
      #     name: Skype Me
      #     link: "skype:echo123?call"
      #   - icon: video
      #     icon_pack: fas
      #     name: Zoom Me
      #     link: "https://zoom.com"
      # Automatically link email and phone or display as text?
      autolink: true
      # Email form provider
      form:
        provider: netlify
        formspree:
          id:
        netlify:
          # Enable CAPTCHA challenge to reduce spam?
          captcha: true
    design:
      columns: "2"
---
