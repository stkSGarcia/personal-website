+++
title = "Linux 下清空 Page cache"
author = "Samuel Garcia"
date = 2018-11-08T00:09:00+08:00
lastmod = 2021-08-24T23:12:35+08:00
tags = ["page-cache", "linux"]
+++

使用下面这条命令：

```sh
sync; echo 1 > /proc/sys/vm/drop_caches
```

<!--more-->

**sync 命令:**

Linux sync 命令用于数据同步，sync 命令是在关闭 Linux 系统时使用的。

Linux 系统中欲写入硬盘的资料有的时候会了效率起见，会写到 filesystem buffer 中，这个 buffer 是一块记忆体空间，如果欲写入硬盘的资料存于此 buffer 中，而系统又突然断电的话，那么资料就会流失了，sync 指令会将存于 buffer 中的资料强制写入硬盘中。

**/proc/sys/vm/drop_caches:**

- To free pagecache, use:

  ```sh
    echo 1 > /proc/sys/vm/drop_caches
  ```

- To free dentries and inodes, use:

  ```sh
    echo 2 > /proc/sys/vm/drop_caches
  ```

- To free pagecache, dentries and inodes, use:

  ```sh
    echo 3 >/proc/sys/vm/drop_caches
  ```
