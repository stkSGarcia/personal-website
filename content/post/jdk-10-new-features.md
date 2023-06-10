---
title: JDK 10 新特性
authors:
  - Shenghui Gu
date: 2018-03-24T19:27:00+08:00
lastmod: 2021-08-24T23:12:34+08:00
tags:
  - Java
---

前几天 JDK 10 正式发布了，距离上一次 JDK 9 发布才没几周时间，但是 JDK 10 还是更新了许多新特性。
下面介绍一下几个比较重要的新特性。

<!-- more -->

## 局部变量类型推断

对于开发者来说，这是 JDK 10 唯一的真正特性。
它向 Java 中引入在其他语言中很常见的 `var` ，比如 JavaScript。
只要编译器可以推断此种类型，你不再需要专门声明一个局部变量的类型。
一个简单的例子是：

```java
var x = new ArrayList();
```

首先，Java 的 `var` 和 JavaScript 的完全不同，不要这样去类比。
Java 的 `var` 是用于局部类型推断的，而不是 JS 那样的动态类型，所以下面这个样子是不行的：

```java
var a = 10;
a = "abc"; //error!
```

其次，这个 `var` 只能用于局部变量声明，在其他地方使用都是错误的。

```java
class C {
    public var a = 10; //error
    public var f() { //error
        return 10;
    }
}
```

所以 `var` 并不会对库的接口产生影响，影响的只可能是内部的实现。

还有些人觉得 `var` 只是一个简单的语法糖，用来少打几个字符。
但其实并不仅仅是这样， `var` 还能够用来弥补 Java 8 lambda 表达式的缺陷。

我们知道 Java 8 的 lambda 表达式不能够捕获可变变量，也就是说下面这个代码是错误的：

```java
int count = 0;
List.of("ice1000", "Glavo").forEach(e -> count += 1); //error
System.out.println(count);
```

之前想要绕过这个限制，我们可以用单元素的数组实现。
而在 Java 10 中我们又多了一种选择：

```java
var context = new Object() {
        int count = 0;
    }
    List.of("ice1000", "Glavo").forEach(e -> context.count += 1);
System.out.println(context.count);
```

除了帮助我们捕获可变参数， `var` 还能够帮助我们实现嵌套函数：

```java
int factorial(int i) {
    var context = new Object() {
            int fact(int i, int accumulator) {
                if (i <= 1)
                    return accumulator;
                else
                    return fact(i - 1, i * accumulator);
            }
        };
    return context.fact(i, 1);
}
```

在使用长的 Stream 操作链的时候，我们也可以把一些操作放在 context 中，从而简化操作链，增强可读性：

```java
int[] parseAndLogInts(List<String> list, int radix) {
    var context = new Object() {
            int parseAndLogInt(String str) {
                System.out.println(str);
                return Integer.parseInt(str, radix);
            }
        };
    return list.stream().mapToInt(context::parseAndLogInt).toArray();
}
```

为了兼容原有代码， `var` 不是一个关键字，而是一个保留类型，这意味着你还是能像这样 `var` 当做一个变量名：

```java
void f() {
    int var = 10;
}
```

`var` 还有一个特殊的特性：在用匿名内部类初始化 `var` 声明的变量时，这个变量会被推断成一个局部的类型，所以你可以这样：

```java
final var o = new Object() {
        public void f() {
            System.out.println("Hello world!");
        }
    };
o.f();
```

注意我们用 `final var` 声明了不可变变量 `o` ，不过其实就算不用 `final var` 声明，你也不能把 `o` 赋值为它的初始值和 `null` 以外的任何值。

## 并行全垃圾回收器 G1

G1 是设计来作为一种低延时的垃圾回收器（但是如果它跟不上旧的堆碎片产生的提升速率的话，将仍然采用完整压缩集合）。
在 JDK9 之前，默认的收集器是并行，吞吐，收集器。
为了减少在使用默认的收集器的应用性能配置文件的差异，G1 现在有一个并行完整收集机制。

> - [JDK 10 的 109 项新特性](http://www.ajiatech.com/news/industryNews/828.html)
> - [如何评价 JDK 10？](https://www.zhihu.com/question/269244201/answer/347062385)
