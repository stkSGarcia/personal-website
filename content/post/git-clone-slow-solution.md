---
title: Git Clone 下载速度慢的解决方法
authors:
  - Shenghui Gu
date: 2018-04-30T20:09:00+08:00
lastmod: 2021-08-24T23:12:34+08:00
tags:
  - Git
---

在国内 Git clone 仓库奇慢无比，通过以下配置可以提升下载速度。

```sh
git config --global http.postBuffer 524288000
```
