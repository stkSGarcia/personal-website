+++
title = "JVM 指令重排对双重校验锁单例模式的影响"
author = "Samuel Garcia"
date = 2018-10-28T18:27:00+08:00
lastmod = 2021-08-24T23:12:35+08:00
tags = ["java"]
+++

下面的双重校验锁单例是线程安全的吗？

```java
public class Singleton {
    private static Singleton instance = null

        private Singleton() {}

        public static Singleton getInstance() {
            if (instance == null) {
                synchronzied(Singleton.class) {
                    if (instance == null) {
                        instance = new Singleton();
                    }
                }
            }
            return instance;
        }
}
```

<!--more-->

## JVM 内存模型

Java 内存模型规定，对于多个线程共享的变量，存储在主内存当中，每个线程都有自己**独立**的工作内存，线程只能访问自己的工作内存，不可以访问其它线程的工作内存。
工作内存中保存了主内存共享变量的**副本**，线程要操作这些共享变量，只能通过操作工作内存中的副本来实现，操作完毕之后再同步回到主内存当中。

### volatile 关键字

很多时候我们需要一个线程对共享变量的改动，其它线程也需要立即得知这个改动该怎么办呢？

Java 为此提供了 volatile 关键字，在声明变量的时候加入 volatile 关键字就可以保证变量的内存可见性，即变量改变对所有的线程都是立即可见的。

volatile 保证可见性的原理是在**每次访问变量时都会进行一次刷新**，因此每次访问都是主内存中最新的版本。
所以 volatile 关键字的作用之一就是保证**变量修改**的实时可见性。

## 指令重排

指令重排序是 JVM 为了优化指令，提高程序运行效率进行的优化操作。
指令重排序包括编译器重排序和运行时重排序。
JVM 规范规定，指令重排序可以在不影响单线程程序执行结果前提下进行。

### 指令重排示例

假设有这么两个共享变量 a 和 b：

```java
private int a;
private int b;
```

在线程 A 中有两条语句对这两个共享变量进行赋值操作：

```java
a = 1;
b = 2;
```

假设当线程 A 对 a 进行复制操作的时候发现这个变量在主内存已经被其它的线程加了访问锁，那么此时线程 A 怎么办？
等待释放锁？不，等待太浪费时间了，它会去尝试进行 b 的赋值操作，b 这时候没被人占用，因此就会先为 b 赋值，再去为 a 赋值，那么执行的顺序就变成了：

```java
b = 2;
a = 1;
```

### 指令重排导致出错

对于在同一个线程内，这样的改变是不会对逻辑产生影响的，但是在多线程的情况下指令重排序会带来问题。
看下面这个情景：

```java
// 在线程 A 中：
context = loadContext();
inited = true;

// 在线程 B 中：
while (!inited ) { //根据线程 A 中对 inited 变量的修改决定是否使用 context 变量
    sleep(100);
}
doSomethingwithconfig(context);
```

假设线程 A 中发生了指令重排序：

```java
inited = true;
context = loadContext();
```

那么 B 中很可能就会拿到一个尚未初始化或尚未初始化完成的 context，从而引发程序错误。

## 指令重排导致单例模式失效

下面是一段双重校验锁单例模式：

```java
public class Singleton {
    private static Singleton instance = null

        private Singleton() {}

        public static Singleton getInstance() {
            if (instance == null) {
                synchronzied(Singleton.class) {
                    if (instance == null) {
                        instance = new Singleton();
                    }
                }
            }
            return instance;
        }
}
```

看似简单的一段赋值语句： `instance = new Singleton();` ，其实 JVM 内部已经转换为多条指令：

```java
memory = allocate(); //1：分配对象的内存空间
ctorInstance(memory); //2：初始化对象
instance = memory; //3：设置 instance 指向刚分配的内存地址
```

但是经过重排序后如下：

```java
memory = allocate(); //1：分配对象的内存空间
instance = memory; //3：设置 instance 指向刚分配的内存地址，此时对象还没被初始化
ctorInstance(memory); //2：初始化对象
```

可以看到指令重排之后，instance 指向分配好的内存放在了前面，而这段内存的初始化被排在了后面，在线程 A 初始化完成这段内存之前，线程 B 虽然进不去同步代码块，但是在同步代码块之前的判断就会发现 instance 不为空，此时线程 B 获得 instance 对象进行使用就可能发生错误。

## 解决方法

volatile 关键字除了可以保证变量修改的可见性之外，还有另一个重要的作用：禁止指令重排序。
变量以关键字 volatile 修饰之后，就会阻止 JVM 对其相关代码进行指令重排，这样就能够按照既定的顺序指执行。

在《深入理解 Java 虚拟机》一书中提到

> volatile 屏蔽指令重排的语义在 JDK1.5 中才被完全修复，此前的 JDK 中即使将变量声明为 volatile 也仍然不能完全避免重排序所导致的问题（主要是 volatile 变量前后的代码仍然存在重排序问题），这点也是在 JDK1.5 之前的 Java 中无法安全地使用 DCL（双锁检测）来实现单例模式的原因。
