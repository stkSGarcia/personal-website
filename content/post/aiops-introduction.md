---
title: AIOps 简介
authors:
  - Shenghui Gu
date: 2020-06-20T21:21:00+08:00
lastmod: 2021-08-24T23:12:36+08:00
tags:
  - AIOps
---

AIOps 是人工智能在软件运维中的应用，即利用机器学习、大数据和自动化决策来完成一系列需要人为进行大量手工干预的传统运维操作流程。
通过对运维数据的算法分析，AIOps 能够帮助运维或 DevOps 团队更智能、更快速的完成运维工作，从而在业务运营和客户受到影响之前，更早的发现软件系统问题并快速解决。
在 DevOps 环境下，运维团队能够通过 AIOps 应对现代 IT 环境产生的大量复杂数据，从而防止中断，维持正常运行时间，实现持续的服务保障。
AIOps 已经成为监控和管理混合、动态、分布式和组件化的现代 IT 环境的关键。

本节将从软件运维的发展历史切入，介绍 AIOps 的必要性、构成及工作方式，并简述了 AIOps 的优势和使用场景。

<!-- more -->

## 软件运维的发展历程

在介绍 AIOps 之前，我们先追溯到软件运维诞生之初。
最早期的运维，也就是手工运维，是以人工加上脚本的方式处理运维问题。
在这一阶段，运维任务相关的决策都是由运维人员做出的，而脚本作为一种辅助手段，仅仅是帮助运维人员执行一些可以机械化的运维任务，以减轻其工作负担。
这种情况下，软件系统规模有限，遇到的问题也相对简单，大多集中在硬件、网络和系统层面，所以对运维的要求并不高。

随着 IT 公司业务场景和体量的复杂化，软件产品交付的频率增大，手工运维的方式已经渐渐满足不了要求了。
例如进行一次业务部署，运维人员可能需要先安装服务器，做系统配置，然后安装产品的软件包，并启停进程，再负载均衡上配置服务等。
因此，为了面对更加复杂化的运维场景，运维人员需要将一个个脚本功能串联起来，形成一个较为完善的运维流程，同时还需要对流程中的执行结果进行判断和校验。
而上述这个过程就是自动化运维的雏形。

随着运维流程化发展，较大 IT 公司进一步对运维流程进行体系化改造，增加其自动化程度，这就步入了自动化运维阶段。
由于技术体系发展，运维所面临的场景复杂度也急剧上升，原有的运维技能如操作系统维护、系统配置、脚本编写已经完全满足不了要求。
同时，由于软件系统复杂度的提升，也需要运维投入更多的精力去关注业务软件架构和应用服务上。
于是，IT 公司对流程化的运维进行了平台化，以适应技术发展趋势，例如 DevOps、SRE (Site Reliability Engineering)、应用运维等。

由于 IT 公司业务体量的巨大变化，软件底层资源也随之快速增长，引发底层技术的变革，如分布式技术，存储计算分离等，软件产品整体的复杂性发生了质的变化。
同时，业务模式及规模决定了用户不再只是使用单产品，而是整个平台层面、多产品的整体使用，所以运维复杂度也会呈几何式增长。
随着这些变化，完全的自动化运维从稳定性，效率，成本，安全等角度已经无法有效支撑其业务发展了。
因此，IT 公司对智能化运维的需求也越来越迫切了。

近年来，机器学习算法的突破、计算能力的提升、海量的数据引发了 AI 革命，而 AIOps 也在这个时期逐渐诞生。
早在 2012 年，全球权威的 IT 研究与顾问咨询公司高德纳公司（Gartner）在一份报告[^1]中提及了 ITOA，其定义为 IT 运维分析（IT Operations Analytics）。
ITOA 通过技术与服务手段，采集、存储、展现海量的 IT 运维数据，并进行有效的推理与归纳得出分析结论。
ITOA 为 AIOps 的发展奠定了基础。
随着时间的推移，在 2016 年 Gartner 将 ITOA 的概念升级为了 AIOps[^2]，其最早的含义是基于算法的 IT 运维（Algorithmic IT Operations）。
这一阶段的 AIOps 平台利用大数据，现代的机器学习技术和其他高级分析技术，通过主动、个性化和动态的洞察力直接或间接地持续地增强 IT 操作功能。
它可以同时使用多个数据源，多种数据收集方法，实时分析技术，深层分析技术以及展示技术。
随着人工智能在多个领域的井喷式发展，Gartner 在 2017 年的一份报告[^3]中将 AIOps 的含义定义为了基于人工智能的 IT 运维（Artificial Intelligence for IT Operations），也就是现在所说的智能运维。

AIOps 将人工智能应用于运维领域，通过融合已有的运维数据，利用机器学习技术以及大数据技术来进一步解决自动化运维所不能解决的问题，真正打破数据烟囱，对监控、自动化、服务台进行支持，提高系统的预判能力、稳定性、降低 IT 成本以更好的支撑业务，并提高企业的产品竞争力。
AIOps 以创造商业价值为导向，对 IT 运维以及业务运维产生持续洞察，为 DevOps 提供持续反馈，加快企业在竞争日趋激烈市场环境中，数字化转型的步伐。
伴随人工智能技术在各个领域的落地，AIOps 是未来解决运维问题的必然方向。

## 为什么需要 AIOps

IT 基础设施从静态的、可预测的物理系统逐渐发展成了由软件定义的、可随时改变和配置的资源。
这就要求运维人员对 IT 基础设施的管理也要采用同样动态的技术和流程。
目前 IT 环境的运维管理的复杂性存在于下面三个层面：

- 系统层面：系统大部分是模块化的、分布式的、动态的，其组成部分是短暂的。
  系统的复杂性成为了 AIOps 的核心复杂性。
- 数据层面：第二层复杂性是由这些系统内部操作的数据产生，例如日志数据、指标数据、调用链数据、事件记录等。
  这些数据由于数据量大、特异性强、种类多、冗余度大，因此复杂度高。
- 工具层面：第三层复杂性来源于监测和管理数据的工具以及系统的复杂性。
  现在的工具越来越多，功能越来越窄，不一定进行数据交互，从而形成操作和数据孤岛。

随着 IT 基础设施的不断发展，基于规则的系统就显得越来越力不从心了。
原因就是它们依赖于一个预先确定的、静态的、同质化的 IT 环境。
AIOps 利用机器学习和大数据技术，让运维团队能够实时了解任何影响服务可用性和性能的问题，包括那些规则之外的、不可预见的问题。

## AIOps 的构成

有效实施 AIOps 的基础是确定使 AIOps 成为可能的核心组件有哪些。
通常情况下，AIOps 的主要组成部分包括：

- 数据收集：成功的 AIOps 会使用不同的来源的运维数据，根据需求转换和聚合数据，有效备份和保留数据，并持续有效的维护数据质量，为数据分析和机器学习提供基础。
- 数据分析：一旦数据被适当地收集和转换，就会执行统计分析，以便从数据中得出见解。
- 机器学习：机器学习是利用从数据分析中得到的见解来做出自动决策的过程。
  机器学习是通过算法实现的，这些算法允许软件自动对数据所表达的信息自动地做出反应。
- 人工智能：这里的人工智能指的是更广泛的自动化决策的范畴，机器学习是其中的一个组成部分。

## AIOps 是如何运作的

并非所有的 AIOps 产品都是一样的。
为了使利益最大化，AIOps 应是一个从所有的 IT 监控源中获得数据的中心化的独立部署平台。
而这样的平台必须由五类算法驱动，以全面自动化和精简运维监控的五个关键维度。

- 数据选择：从 IT 环境产生的大量高冗余、高噪音的 IT 数据中挑选出可能有问题的数据。
  而这往往意味着要过滤掉高达 99% 的数据。
- 模式发现：对选定的、有意义的数据进行关联，找到它们之间的联系，并进行分组，以便进一步分析。
- 推理：找出问题的根源和反复出现的问题，以便对发现的问题采取行动。
- 协作：通知适当的操作人员和团队，并促进他们之间的合作，特别是当个人在地理上分散时。
  同时需要保存事故数据，以加快未来对类似问题的诊断。
- 自动化：尽可能实现自动化响应和补救，使解决方案更加精确和快速。

在现实环境中，AIOps 平台从许多不同来源获取 IT 环境组件的异构数据，这些组件包括网络、应用、基础设施、云实例、存储等。
AIOps 利用熵算法去除噪音和重复，只选择真正相关的数据，大大减少了运维团队必须处理的警报数量，并消除了由于冗余的工单传送到不同团队而造成的重复工作。

然后，AIOps 利用各种标准，如文本、时间和拓扑结构，将这些相关信息进行分组和关联。
接下来，它发现数据中的模式，并推断哪些数据项标志着原因，哪些标志着事件。
平台将分析结果传达给虚拟协作环境，参与解决事件的每个人都可以访问所有相关数据。
这些虚拟团队可以快速组建，使不同的专家能够围绕一个跨越技术或组织边界的问题进行解决。

之后，他们可以迅速决定修复措施，并选择自动响应，以快速、准确地解决事件。
AIOps 还能提高自动化程度，使工作流程在有或没有人工干预的情况下被触发。
AIOps 平台存储了每个固定事件的原因和解决方案，并利用这些知识帮助运维团队诊断原因，并为未来的问题开出解决方案。

## AIOps 的优势

AIOps 为运维团队提供了所需的速度和敏捷性，以确保关键服务的正常运行时间，并提供最佳的用户体验。
基于规则的运维流程的脆弱性，信息孤岛，以及重复性的人工操作，使得运维人员在没有 AIOps 的环境下很难完成运维任务。
以下是 AIOps 的一些好处：

- AIOps 可以消除噪音和干扰，使运维人员能够专注于重要的事情，而不会被无关的警报所干扰。
  这加快了对影响服务的问题的检测和解决速度，并防止出现影响销售和客户体验的中断。
- 通过关联多个数据源的信息，AIOps 消除了信息孤岛，并在整个 IT 环境内部和云端提供了一个整体的、上下文化的视野。
- 通过促进不同专家和服务所有者之间的无摩擦、跨团队协作，AIOps 加快了诊断和解决时间，最大限度地减少了对最终用户的干扰。
- 通过先进的机器学习技术在后台捕捉有用的信息，以进一步提高对未来情况的处理。
- 通过知识循环和根因识别，自动化工作流程以应对反复出现的情况，使运维团队更接近无工单和自我修复的环境。

## AIOps 的使用场景

通过使用数据收集、数据分析和机器学习相结合的完整 AIOps 解决方案，运维团队可以支持以下几个关键使用场景：

- 异常检测：AIOps 最基本的使用案例就是检测数据中的异常，然后根据需要对它们做出反应。
- 根因分析：AIOps 能够帮助运维团队自动执行根本原因分析，从而快速解决问题。
- 预测：AIOps 可以让工具能对未来进行自动预测，例如用户流量在特定的时间点可能会怎样的变化，然后做出相应的反应。
- 报警管理：AIOps 在帮助运维团队应对他们必须处理的大量警报，以支持正常的运维方面发挥着越来越重要的作用。
- 智能修复：AIOps 通过自动化工具驱动闭环的故障修复，而不依赖于运维人员。

[^1]: <https://www.gartner.com/en/documents/2158125>
[^2]: <https://www.gartner.com/en/documents/3263717>
[^3]: <https://www.gartner.com/en/documents/3770467>
