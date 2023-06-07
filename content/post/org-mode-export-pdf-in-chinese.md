+++
title = "Org mode 导出中文 PDF"
author = "Samuel Garcia"
date = 2019-01-29T01:32:00+08:00
lastmod = 2021-08-24T23:12:35+08:00
tags = ["org-mode", "latex", "emacs"]
+++

只要在文件开头加入以下代码：

<!--more-->

```org
#+LATEX_COMPILER: xelatex
#+LATEX_HEADER: \usepackage{xeCJK}
```
