---
title: 编译中文 LaTeX
authors:
  - Shenghui Gu
date: 2017-09-22T09:15:00+08:00
lastmod: 2021-08-24T23:21:54+08:00
tags:
  - LaTeX
---

之前想用中文写 LaTeX，查了几次总是忘记，在此记录。

只要在文件开头加入以下代码：

```tex
% !TEX program = xelatex
\documentclass{ctexart}
```
