---
title: 什么会和“Ops”碰撞出火花？
authors:
  - Shenghui Gu
date: 2017-09-09T08:12:00+08:00
lastmod: 2021-08-24T23:12:32+08:00
tags:
  - DevOps
  - AIOps
---

最近 AIOps 非常火，加上之前对 DevOps 做了一些研究，现在找了一些带有 Ops 的词，在此做了一些整理。

<!-- more -->

## DevOps

DevOps（英文 Development 和 Operations 的组合）是一组过程、方法与系统的统称，用于促进开发（应用程序/软件工程）、技术运营和质量保障（QA）部门之间的沟通、协作与整合。
它的出现是由于软件行业日益清晰地认识到：为了按时交付软件产品和服务，开发和运营工作必须紧密合作。

## AIOps

AIOps，也就是基于算法的 IT 运维（Algorithmic IT Operations），是由 Gartner 定义的新类别，源自业界之前所说的 ITOA (IT Operations and Analytics)。
我们已经到达了这样的一个时代，数据科学和算法正在被用于自动化传统的 IT 运维任务和流程。
算法被集成到工具里，帮助企业进一步简化运维工作，把人类从耗时又容易出错的流程中解放出来。人们不再需要在遗留的管理系统中定义和管理无穷无尽的规则和过滤器。

> - [What are algorithmic IT operations (AIOps)?](https://www.quora.com/What-are-algorithmic-IT-operations-AIOps)
> - [AIOps 是什么？它与 AI 有什么关系？](http://www.infoq.com/cn/news/2017/06/AIOps-ai-relation)

## DevSecOps

DevSecOps 是糅合了开发、安全及运营理念以创建解决方案的全新方法，是 DevOps 与 SecOps 的结合。
DevSecOps 的作用和意义建立在 **每个人都对安全负责** 的理念之上，其目标是在不影响安全需求的情况下快速的执行安全决策，将决策传递至拥有最高级别环境信息的人员。

DevSecOps 宣言：

1. CIO 驱动
2. 不同团队间的相互协作
3. 专注于风险，而非安全

> - [What is DevSecOps?](http://www.devsecops.org/blog/2015/2/15/what-is-devsecops)
> - [The DevOps concept: NoOps, DataOps and what comes next](http://devopsagenda.techtarget.com/opinion/The-DevOps-concept-NoOps-DataOps-and-what-comes-next)
> - [DevSecOps 简介（一）](http://blog.oneapm.com/apm-tech/643.html)
> - [什么是 DevSecOps？系列（一）](http://blog.oneapm.com/apm-tech/507.html)

## BizDevOps

BizDevOps，也被称作 DevOps 2.0，是一种鼓励开发、运维和业务团队携手合作的软件开发方式，使组织能够更快地开发软件，更好地响应用户需求，最终实现收益最大化。

> - [BizDevOps (Business, Development and Operations)](http://searchsoftwarequality.techtarget.com/definition/BizDevOps-Business-Development-and-Operations)

## DataOps

DataOps (data operations) 是一种设计、实施和维护分布式数据架构的方法，这些数据架构支持实际生产中大多数的开源工具和框架。
受 DevOps 运动的启发，DataOps 力求加快运行在大数据处理框架上的应用生产。
像 DevOps 一样，DataOps 旨在打破 IT 运维和软件开发团队的壁垒，鼓励业界利益相关者同数据工程师，数据科学家和分析师之间的合作，以最灵活，最有效的方式使用该组织的数据来实现正面的业务成果。

> - [DataOps (data operations)](http://searchdatamanagement.techtarget.com/definition/DataOps)
> - [The DevOps concept: NoOps, DataOps and what comes next](http://devopsagenda.techtarget.com/opinion/The-DevOps-concept-NoOps-DataOps-and-what-comes-next)
> - [Wiki](https://en.wikipedia.org/wiki/DataOps)

## NoOps

NoOps (no operations) 是一种理念，IT 环境可以从基础架构进行自动化和抽象化，不需要专门的团队来管理内部软件。
在 NoOps 场景下，维护和一些其他的由运维执行的任务将会被自动实施。
NoOps 背后的两个主要驱动力是 IT 自动化和云计算。

> - [NoOps](http://searchcloudapplications.techtarget.com/definition/noops)
> - [The DevOps concept: NoOps, DataOps and what comes next](http://devopsagenda.techtarget.com/opinion/The-DevOps-concept-NoOps-DataOps-and-what-comes-next)

## ChatOps

ChatOps 在 GitHub 上广受赞誉，是指由对话驱动的开发。
将工具植入到对话当中，使用被关键插件和脚本改良过的聊天机器人，团队能够自动执行任务和协作，效果更好、成本更低、速度更快。

以下是项目经理的观点：在聊天室里，团队成员输入命令来配置机器人，它们通过自定义脚本和插件来执行命令，从代码部署到安全事件响应再到团队成员提醒，范围极广。随着命令被不断执行，整个团队协作也实时进行。

> - [ChatOps](http://searchitoperations.techtarget.com/definition/ChatOps)
> - [ChatOps and VoiceOps make DevOps integration easier than ever](http://devopsagenda.techtarget.com/opinion/ChatOps-and-VoiceOps-make-DevOps-integration-easier-than-ever)
> - [DevOps 理念升级，ChatOps 概述及实践经验](http://www.csdn.net/article/a/2017-04-10/15926999)
> - [ChatOps 是什么？该如何使用呢？](http://blog.daocloud.io/chatops-pagerduty/)

## VoiceOps

相对于 ChatOps，VoiceOps 更进了一步，它将虚拟语音助手集成到了运维工具中。

> - [ChatOps and VoiceOps make DevOps integration easier than ever](http://devopsagenda.techtarget.com/opinion/ChatOps-and-VoiceOps-make-DevOps-integration-easier-than-ever)

## SecOps

同 DevOps 统一开发和运维类似，SecOps 是解决安全团队和运维团队隔阂的管理方法。
SecOps 将安全和运维团队联系起来，共同分担责任，分享流程和使用工具，以此在不牺牲安全性的前提下维持正常运行时间和性能。

> - [What is SecOps?](https://www.govloop.com/what-is-secops/)

## WebOps

WebOps (Web operations) 是处理 Web 应用和其支持系统中复杂事务的 IT 系统管理领域。
WebOps 工程领域包括应用部署、管理、维护、配置和修复。

优秀的 WebOps 工程师会对以下技术有深入的理解：网络、路由、交换、防火墙、负载均衡、高可用、灾难恢复、TCP 和 UDP 服务、NOC 管理、硬件规格、多种不同 UNIX 发行版、多种 Web 服务器技术、缓存技术、多种数据库、存储基础设施、密码学、算法、容量规划。

> - [WebOps (Web operations)](http://whatis.techtarget.com/definition/WebOps-Web-operations)

## HumanOps

HumanOps 是一套关注运行基础设施人力方面的原则。
它强调了运行系统团队的重要性，而不仅仅是系统本身。
基础设施的健康状况不仅仅是硬件、软件、自动化和正常运行时间 —— 它还包括团队的健康和福利。
HumanOps 的目标是改善和保持团队的健康：促进沟通，减少疲劳和减轻压力。

> - [HumanOps](https://github.com/HumanOps/HumanOps/blob/master/HumanOps.rst)
> - [DevOps and HumanOps: Efficiency meets empathy](http://devopsagenda.techtarget.com/opinion/DevOps-and-HumanOps-Efficiency-meets-empathy)

## DesignOps

基于 DevOps 的理念和实践，DesignOps 有助于优化开发者和设计师之间的沟通和协作，以便更快的生产更好的产品。

> - [DesignOps: Bridging the developer, designer communication gap](http://searchsoftwarequality.techtarget.com/news/450421998/DesignOps-Bridging-the-developer-designer-communication-gap)

## Anti-DevOps

Anti-DevOps 是一种反对 DevOps 革命的理念。
已经有 DevOps 的批评者抱怨 DevOps 是在“杀死开发人员”，或者 DevOps 只适用于像 Netflix 和 Google 这样的大型组织。
如果这样的情绪大量聚集，软件组织可能会重新采用传统软件交付模式而推迟 DevOps 的实施。

> - [The DevOps concept: NoOps, DataOps and what comes next](http://devopsagenda.techtarget.com/opinion/The-DevOps-concept-NoOps-DataOps-and-what-comes-next)
