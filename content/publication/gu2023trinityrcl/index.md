---
title: "TrinityRCL: Multi-Granular and Code-Level Root Cause Localization Using Multiple Types of Telemetry Data in Microservice Systems"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Shenghui Gu
  - Guoping Rong
  - Tian Ren
  - He Zhang
  - Haifeng Shen
  - Yongda Yu
  - Xian Li
  - Jian Ouyang
  - Chunan Chen

# Author notes (optional)
# author_notes:
#   - "Equal contribution"
#   - "Equal contribution"

date: 2023-05-01T00:00:00Z
doi: 10.1109/tse.2023.3241299

# Schedule page publish date (NOT publication's date).
# publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: _IEEE Transactions on Software Engineering_, 49(5)
publication_short: ""

abstract: >-
  The microservice architecture has been commonly adopted by large scale software systems exemplified by a wide range of online services. Service monitoring through anomaly detection and root cause analysis (RCA) is crucial for these microservice systems to provide stable and continued services. However, compared with monolithic systems, software systems based on the layered microservice architecture are inherently complex and commonly involve entities at different levels of granularity. Therefore, for effective service monitoring, these systems have a special requirement of multi-granular RCA. Furthermore, as a large proportion of anomalies in microservice systems pertain to problematic code, to timely troubleshoot these anomalies, these systems have another special requirement of RCA at the finest code-level. Microservice systems rely on telemetry data to perform service monitoring and RCA of service anomalies. The majority of existing RCA approaches are only based on a single type of telemetry data and as a result can only support uni-granular RCA at either application-level or service-level. Although there are attempts to combine metric and tracing data in RCA, their objective is to improve RCA's efficiency or accuracy rather than to support multi-granular RCA. In this article, we propose a new RCA solution _TrinityRCL_ that is able to localize the root causes of anomalies at multiple levels of granularity including application-level, service-level, host-level, and metric-level, with the unique capability of code-level localization by harnessing all three types of telemetry data to construct a causal graph representing the intricate, dynamic, and nondeterministic relationships among the various entities related to the anomalies. By implementing and deploying _TrinityRCL_ in a real production environment, we evaluate _TrinityRCL_ against two baseline methods and the results show that _TrinityRCL_ has a significant performance advantage in terms of accuracy at the same level of granularity with comparable efficiency and is particularly effective to support large-scale systems with massive telemetry data.

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
url_slides: ""
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
