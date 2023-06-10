---
title: "Locating Anomaly Clues for Atypical Anomalous Services: An Industrial Exploration"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Guoping Rong
  - Hao Wang
  - Shenghui Gu
  - Yangchen Xu
  - Jialin Sun
  - Dong Shao
  - He Zhang

# Author notes (optional)
# author_notes:
#   - "Equal contribution"
#   - "Equal contribution"

date: 2022-06-01T00:00:00Z
doi: 10.1109/TDSC.2022.3181143

# Schedule page publish date (NOT publication's date).
# publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: _IEEE Transactions on Dependable and Secure Computing_
publication_short: ""

abstract: >-
  Continuity and steadiness are vital for services with massive users, which requires the anomalies of services should be detected and resolved in a timely manner. Our previous work proposed a tool, namely _ImpAPTr (Impact Analysis based on Pruning Tree)_, to identify the combination of multiple dimensional attributes as the clues leading to the root cause of service anomalies. However, _ImpAPTr_ applies a threshold driven strategy, i.e. it needs to be triggered by a ≥ 0.05% drop of the success rate of the service calls (abbr. _SRSC_), which may face problems in an atypical yet pervasive situation in field application. For example, the combination of trivial anomalies (i.e. each causes a drop less than 0.05% to _SRSC_) can lead to a far more than 0.05% drop on _SRSC_. Besides, a suitable threshold is usually hard to be determined, etc. To address these problems, we propose a new method, namely _ImpAPTr+_ in this paper to free the constraint of the 0.05% threshold. The basic idea is to involve time dimension and identify clues across multiple time intervals of data. We performed evaluation on three typical methods (i.e. _ImpAPTr+_, _R-Adtributor_ and _Squeeze_) with both production environment dataset and simulation dataset. The former dataset is directly retrieved from the service monitoring data in _Meituan_, one of the largest on-line service providers worldwide. The latter dataset is fabricated also using the monitoring data from the same company. The results indicate: (1) _ImpAPTr+_ outperforms previous approaches to a large degree in terms of accuracy. (2) Both _ImpAPTr+_ and _R-Adtributor_ are able to find proper clues within seconds. (3) _ImpAPTr+_ tends to find proper clues with shorter time intervals (i.e. less data), which implies that the method is more suitable for near real-time monitoring scenarios.

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
