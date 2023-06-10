---
title: Windows 下使用 Powershell 批量重命名文件
authors:
  - Shenghui Gu
date: 2018-03-18T18:47:00+08:00
lastmod: 2021-08-24T23:12:33+08:00
tags:
  - Powershell
  - Windows
---

当我们下载了一部电视剧或是动漫时，通常文件名非常长，会包含视频的分辨率、字幕组等信息，但是我们通常只会关心这是第几集。。。

<!-- more -->

于是就开始寻找 Windows 下批量重命名的方法。
虽然 Windows 下的命令行没有 Linux 下方便，但是还是提供了必备的功能。

以下就是通过 Powershell 实现批量正则重命名文件。

```sh
Get-ChildItem *.mp4 | Rename-Item -NewName { $_.name -replace '.*Vol\.([0-9]{1}).*', 'Video_$1.mp4' }
```

其中管道前是列出所有 mp4 文件。
`Rename-Item` 的一般形式是 `Rename-Item -Path <String> -NewName <String>` 。
大括号内是通过正则替换字符串。

另外 `Get-ChildItem` 的别名是 `ls` ， `Rename-Item` 的别名是 `rni` 。
