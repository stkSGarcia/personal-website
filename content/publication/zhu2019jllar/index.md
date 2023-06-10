---
title: "JLLAR: A Logging Recommendation Plug-in Tool for Java"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Jing Zhu
  - Guoping Rong
  - Guocheng Huang
  - Shenghui Gu
  - He Zhang
  - Dong Shao

# Author notes (optional)
# author_notes:
#   - "Equal contribution"
#   - "Equal contribution"

date: 2023-10-28T00:00:00Z
doi: 10.1145/3361242.3361261

# Schedule page publish date (NOT publication's date).
# publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In _Asia-Pacific Symposium on Internetware_
publication_short: In _Internetware_

abstract: >-
  Logs are the execution results of logging statements in software systems after being triggered by various events, which is able to capture the dynamic behavior of software systems during runtime and provide important information for software analysis, e.g., issue tracking, performance monitoring, etc. Obviously, to meet this purpose, the quality of the logs is critical, which requires appropriately placement of logging statements. Existing research on this topic reveals that _where to log?_ and _what to log?_ are two most concerns when conducting logging practice in software development, which mainly relies on developers' personal skills, expertise and preference, rendering several problems impacting the quality of the logs inevitably. One of the reasons leading to this phenomenon might be that several recognized best practices (strategies as well) are easily neglected by software developers. Especially in those software projects with relatively large number of participants. To address this issue, we designed and implemented a plug-in tool (i.e., _JLLAR_) based on the Intellij IDEA, which applied machine learning technology to identify and create a set of rules reflecting commonly recognized logging practices. Based on this rule set, _JLLAR_ can be used to scan existing source code to identify issues regarding the placement of logging statements. Moreover, _JLLAR_ also provides automatic code completion and semi code completion (i.e., to provide recommendations) regarding logging practice to support software developers during coding.

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
url_slides: zhu2019jllar_presentation.pptx
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
