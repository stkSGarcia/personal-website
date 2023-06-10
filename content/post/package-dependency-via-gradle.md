---
title: 通过 Gradle 打包外部依赖
authors:
  - Shenghui Gu
date: 2018-03-03T19:04:00+08:00
lastmod: 2021-08-24T23:12:33+08:00
tags:
  - Gradle
---

有时候我们需要通过 Gradle 将依赖打包进 Jar 包中，下面代码中的 `fatJar` 任务可以实现此功能。

<!-- more -->

```groovy
group 'com.example'
version '0.1.0'

apply plugin: 'java'

sourceCompatibility = 1.8

repositories {
    mavenCentral()
}

dependencies {
    compile fileTree(dir: 'lib', include: '*.jar')
    compile group: 'org.apache.kafka', name: 'kafka-clients', version: '1.0.0'
    compile group: 'org.slf4j', name: 'slf4j-simple', version: '1.7.25'
    testCompile group: 'junit', name: 'junit', version: '4.12'
}

tasks.withType(JavaCompile) {
    options.encoding = "UTF-8"
}

task fatJar(type: Jar) {
    manifest {
        attributes 'Main-Class': 'com.example.stk.Main'
    }
    from { configurations.compile.collect { it.isDirectory() ? it : zipTree(it) } }
    with jar
}
```

另外， `dependencies` 代码块中的 `fileTree` 用于将外部的依赖包通过 Gradle 管理。

`attributes 'Main-Class': 'com.example.stk.Main'` 指定 Jar 包的主类。
