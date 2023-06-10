---
title: 通过 Java API 实现 Kafka Consumer 从最开始消费
authors:
  - Shenghui Gu
date: 2018-03-06T22:07:00+08:00
lastmod: 2021-08-24T23:12:33+08:00
tags:
  - Kafka
  - Java
---

之前写项目的时候需要通过 Java API 实现 Consumer 每次都从最开始消费，也就是将 Kafka topic 下所有 partition 的 offset 重置到最初位置。

<!-- more -->

这个功能类似 shell 下的命令：

```sh
./kafka-console-consumer.sh --bootstrap-server serverip:9092 --topic topic --from-beginning
```

Kafka 的 JavaDoc 中提到可以使用 `seekToBeginning(Collection<TopicPartition>)` 方法来实现 `--from-beginning` 的功能，但是文档中没有详细说明如何使用，只是提及这个方法“evaluates lazily”， 只有在调用 `poll(long)` 或 `position(TopicPartition)` 的时候才重置 offset 到开头。
所以直接在 `subscribe(Pattern pattern)` 后调用是不起作用的。

正确的方法应该是在 Partition 分配后的回掉函数中重置 offset，具体代码如下：

```java
consumer.subscribe(Collections.singletonList(topic), new ConsumerRebalanceListener() {
        @Override
        public void onPartitionsRevoked(Collection<TopicPartition> partitions) {
        }

        @Override
        public void onPartitionsAssigned(Collection<TopicPartition> partitions) {
            consumer.seekToBeginning(partitions);
        }
    });
```
