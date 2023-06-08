---
title: "TrinityRCL: Multi-Granular and Code-Level Root Cause Localization Using
  Multiple Types of Telemetry Data in Microservice Systems"
publication_types:
  - "2"
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
doi: 10.1109/tse.2023.3241299
publication: IEEE Transactions on Software Engineering
publication_short: TSE
abstract: The microservice architecture has been commonly adopted by large scale
  software systems exemplified by a wide range of online services. Service
  monitoring through anomaly detection and root cause analysis (RCA) is crucial
  for these microservice systems to provide stable and continued services.
  However, compared with monolithic systems, software systems based on the
  layered microservice architecture are inherently complex and commonly involve
  entities at different levels of granularity. Therefore, for effective service
  monitoring, these systems have a special requirement of multi-granular RCA.
  Furthermore, as a large proportion of anomalies in microservice systems
  pertain to problematic code, to timely troubleshoot these anomalies, these
  systems have another special requirement of RCA at the finest code-level.
  Microservice systems rely on telemetry data to perform service monitoring and
  RCA of service anomalies. The majority of existing RCA approaches are only
  based on a single type of telemetry data and as a result can only support
  uni-granular RCA at either application-level or service-level. Although there
  are attempts to combine metric and tracing data in RCA, their objective is to
  improve RCA’s efficiency or accuracy rather than to support multi-granular
  RCA. In this paper, we propose a new RCA solution *TrinityRCL* that is able to
  localize the root causes of anomalies at multiple levels of granularity
  including application-level, service-level, host-level, and metric-level, with
  the unique capability of code-level localization by harnessing all three types
  of telemetry data to construct a causal graph representing the intricate,
  dynamic, and nondeterministic relationships among the various entities related
  to the anomalies. By implementing and deploying *TrinityRCL* in a real
  production environment, we evaluate *TrinityRCL* against two baseline methods
  and the results show that *TrinityRCL* has a significant performance advantage
  in terms of accuracy at the same level of granularity with comparable
  efficiency and is particularly effective to support large-scale systems with
  massive telemetry data.
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
date: 2023-06-08T10:05:19.317Z
---
