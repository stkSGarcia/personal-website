+++
title = "Git Clone 下载速度慢的解决方法"
author = "Samuel Garcia"
date = 2018-04-30T20:09:00+08:00
lastmod = 2021-08-24T23:12:34+08:00
tags = ["git"]
+++

在国内 Git clone 仓库奇慢无比，通过以下配置可以提升下载速度。

```sh
git config --global http.postBuffer 524288000
```
