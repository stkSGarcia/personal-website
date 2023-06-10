---
title: How Is Logging Practice Implemented in Open Source Software Projects? A Preliminary Exploration

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Guoping Rong
  - Shenghui Gu
  - He Zhang
  - Dong Shao
  - WanggenLiu

# Author notes (optional)
# author_notes:
#   - "Equal contribution"
#   - "Equal contribution"

date: 2018-11-26T00:00:00Z
doi: 10.1109/aswec.2018.00031

# Schedule page publish date (NOT publication's date).
# publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In _Australasian Software Engineering Conference_
publication_short: In _ASWEC_

abstract: >-
  _Background:_ Logs are the footprints that software systems produce during runtime, which can be used to understand the dynamic behavior of these software systems. To generate logs, logging practice is accepted by developers to place logging statements in the source code of software systems. Compared to the great number of studies on log analysis, the research on logging practice is relatively scarce, which raises a very critical question, i.e. as the original intention, can current logging practice support capturing the behavior of software systems effectively? _Aims:_ To answer this question, we first need to understand how logging practices are implemented these software projects. _Method:_ In this paper, we carried out an empirical study to explore the logging practice in open source software projects so as to establish a basic understanding on how logging practice is applied in real world software projects. The _density_, _log level (what to log?)_ and _context (where to log?)_ are measured for our study. _Results:_ Based on the evidence we collected in 28 top open source projects, we find the logging practice is adopted highly inconsistently among different developers both across projects and even within one project in terms of the density and log levels of logging statements. However, the choice of what context the logging statements to place is consistent to a fair degree. _Conclusion:_ Both the inconsistency in _density_ and _log level_ and the convergence of context have forced us to question whether it is a reliable means to understand the runtime behavior of software systems via analyzing the logs produced by the current logging practice.

# Summary. An optional shortened abstract.
# summary:

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ""
url_code: ""
url_dataset: ""
url_poster: ""
url_project: ""
url_slides: rong2018logging_presentation.pptx
url_source: ""
url_video: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
