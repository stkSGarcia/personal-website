+++
title = "Scala 学习资料"
author = "Samuel Garcia"
date = 2018-04-15T18:13:00+08:00
lastmod = 2021-08-26T23:43:28+08:00
tags = ["scala"]
+++

记录一些 Scala 的学习资料，感谢@hongjiang_wang 的整理。
[原帖地址](http://hongjiang.info/scala/)

<!--more-->

## Akka

- [Actor 里的偏函数与性能](http://hongjiang.info/akka-in-practice-1/)
- [Patterns.ask 是使用一个临时创建的 actor 发消息而非自身](http://hongjiang.info/akka-patterns-ask-with-temporary-actor/)
- [对 actor 的邮箱计数](http://hongjiang.info/akka-mailbox-counter-extension/)
- [Never ever block an actor](http://hongjiang.info/never-ever-block-an-actor/)

## 模式匹配

- [话说模式匹配(1) 什么是模式？](http://hongjiang.info/scala-pattern-matching-1/)
- [话说模式匹配(2) scala 里是怎么实现的?](http://hongjiang.info/scala-pattern-matching-2/)
- [话说模式匹配(3) 模式匹配的核心功能是解构！](http://hongjiang.info/scala-pattern-matching-3/)
- [话说模式匹配(4) 赋值语句与模式匹配](http://hongjiang.info/scala-pattern-matching-4/)
- [话说模式匹配(5) for 表达式中的模式匹配](http://hongjiang.info/scala-pattern-matching-5/)
- [话说模式匹配(6) case 类的细节](http://hongjiang.info/scala-pattern-matching-6/)
- [话说模式匹配(7) 一个构造器模式的例子(by case class)](http://hongjiang.info/scala-pattern-matching-7/)
- [话说模式匹配(8) 一个抽取器的例子](http://hongjiang.info/scala-pattern-matching-8/)

## 类型相关

- [scala 类型系统：1) 类型与类](http://hongjiang.info/scala-type-and-class/)
- [scala 类型系统：2) classOf 与 getClass 方法的差异](http://hongjiang.info/scala-type-system-classof-and-getclass/)
- [scala 类型系统：3) 单例类型](http://hongjiang.info/scala-type-system-singleton-type/)
- [scala 类型系统：4) 内部类，路径依赖类型&类型投影](http://hongjiang.info/scala-type-system-inner-type-and-type-projection/)
- [scala 类型系统：5) 结构类型](http://hongjiang.info/scala-type-system-structural-type/)
- [scala 类型系统：6) 复合类型与 with 关键字](http://hongjiang.info/scala-type-system-compund-type/)
- [scala 类型系统：7) 中缀类型](http://hongjiang.info/scala-type-system-infix-type/)
- [scala 类型系统：8) type 关键字](http://hongjiang.info/scala-type-system-type-keyword/)
- [scala 类型系统：9) this 别名&自身类型](http://hongjiang.info/scala-type-system-self-type/)
- [scala 类型系统：10) 交集类型与联合类型](http://hongjiang.info/scala-intersection-type-and-union-type/)
- [scala 类型系统：11) upper bounds & lower bounds](http://hongjiang.info/scala-upper-bounds-and-lower-bounds/)
- [scala 类型系统：12) view bounds](http://hongjiang.info/scala-type-system-view-bounds/)
- [scala 类型系统：13) context bounds](http://hongjiang.info/scala-type-system-context-bounds/)
- [scala 类型系统：14) multiple bounds](http://hongjiang.info/scala-type-system-multiple-bounds/)
- [scala 类型系统：15) 协变与逆变](http://hongjiang.info/scala-covariance-and-contravariance/)
- [scala 类型系统：16) 函数类型](http://hongjiang.info/scala-function-type/)
- [scala 类型系统：17) 结构类型的细节问题](http://hongjiang.info/scala-structural-type-detail/)
- [scala 类型系统：18) 不稳定(volatile)类型](http://hongjiang.info/scala-type-system-volatile-type/)
- [scala 类型系统：19) Manifest 与 TypeTag](http://hongjiang.info/scala-type-system-manifest-vs-typetag/)
- [scala 类型系统：20) 数组类型](http://hongjiang.info/scala-type-system-array-type/)
- [scala 类型系统：21) type specialization 与类爆炸](http://hongjiang.info/scala-type-specialization/)
- [scala 类型系统：22) 类型约束与特定方法](http://hongjiang.info/scala-type-contraints-and-specialized-methods/)
- [scala 类型系统：23) 用类型证明实现联合类型](http://hongjiang.info/scala-type-evidence-and-union-type/)
- [scala 类型系统：24) 理解 higher-kinded-type](http://hongjiang.info/scala-higher-kinded-type/)
- [scala 类型系统：25) type lambda](http://hongjiang.info/scala-type-lambda/)
- [scala 类型系统：26) type classes 模式](http://hongjiang.info/scala-type-classes-pattern/)
- [scala 类型系统：27) 回顾常见的 type classes](http://hongjiang.info/scala-type-classes-review/)
- [scala 类型系统：28) 依赖类型](http://hongjiang.info/scala-type-system-dependent-types/)
- [scala 类型系统：case class 与代数数据类型](http://hongjiang.info/scala-case-class-and-algebraic-data-type/)
- [scala 类型系统：类型推导](http://hongjiang.info/scala-type-inference/)
- [scala 类型系统：柯里-霍华德同构](http://hongjiang.info/scala-curry-howard-isomorphism/)
- [scala 类型系统：值类型与数组](http://hongjiang.info/scala-value-class-in-array/)
- [scala 类型系统：Null 与 Nothing，造型问题](http://hongjiang.info/scala-null-and-nothing/)
- [scala 类型系统：值类型的细节](http://hongjiang.info/scala-value-classes-detail/)
- [scala 类型系统：通用特质(universal traits)](http://hongjiang.info/scala-universal-traits/)
- [scala 类型系统：值类型的装箱问题](http://hongjiang.info/scala-value-class-boxing-question/)
- [scala 类型系统：值类型的一些限制](http://hongjiang.info/scala-value-classes/)

## Shapeless

- [shapeless(1): 从方法与函数的多态谈起](http://hongjiang.info/shapeless-1-polymorphic-question/)
- [shapeless(2): 对函数(值)实现参数化多态](http://hongjiang.info/shapeless-2-polymorphic-function-impl/)

## 类型推导相关

- [泛型方法转换为部分应用函数时的类型推导问题](http://hongjiang.info/generic-methods-2-partially-applied-functions/)

## Spray

- [spray 中的 Magnet 模式: typeclass 的一种特定方式](http://hongjiang.info/spray-magnet-pattern/)

## Monads & Monoids

- [我所理解的 monad(0)](http://hongjiang.info/understand-monad-0/)
- [我所理解的 monad(1)：半群(semigroup)与幺半群(monoid)](http://hongjiang.info/semigroup-and-monoid/)
- [我所理解的 monad(2)：fold 与 monoid](http://hongjiang.info/fold-and-monoid/)
- [我所理解的 monad(3)：半群(semigroup)与并行运算](http://hongjiang.info/semigroup-and-parallel/)
- [我所理解的 monad(4)：函子(functor)是什么](http://hongjiang.info/understand-monad-4-what-is-functor/)
- [我所理解的 monad(5)：自函子(Endofunctor)是什么](http://hongjiang.info/understand-monad-5-what-is-endofunctor/)
- [我所理解的 monad(6)：从组合子(combinator)说起](http://hongjiang.info/understand-monad-6-combinator/)
- [我所理解的 monad(7)：把 monad 看做行为的组合子](http://hongjiang.info/understand-monad-7-action-combinator/)

## 翻译&笔记

- [Programming in Scala 的阅读笔记](http://hongjiang.info/programming-in-scala-notes/)
- [Effective Scala 中文版](http://hongjiang.info/effective-scala-chinese/)
- [翻译 monads-are-elephants 第一部分](http://hongjiang.info/monads-are-elephants-part1-chinese)
- [翻译 monads-are-elephants 第二部分](http://hongjiang.info/monads-are-elephants-part2-chinese)
- [翻译 monads-are-elephants 第三部分](http://hongjiang.info/monads-are-elephants-part3-chinese)

## Scala pitfalls

- [scala 雾中风景(0): 序](http://hongjiang.info/scala-pitfalls-0/)
- [scala 雾中风景(1): lambda 表达式的缩写](http://hongjiang.info/scala-pitfalls-1/)
- [scala 雾中风景(2): 小括号与花括号](http://hongjiang.info/scala-pitfalls-2/)
- [scala 雾中风景(3): for 表达式的背后](http://hongjiang.info/scala-pitfalls-3/)
- [scala 雾中风景(4): Unit 类型](http://hongjiang.info/scala-pitfalls-4/)
- [scala 雾中风景(5): 中缀表达](http://hongjiang.info/scala-pitfalls-5/)
- [scala 雾中风景(6): 内部类与模式匹配](http://hongjiang.info/scala-pitfalls-6/)
- [scala 雾中风景(7): val x:Int = x + 1 的问题](http://hongjiang.info/scala-pitfalls-7/)
- [scala 雾中风景(8): 高阶函数与 Unit 的谜题](http://hongjiang.info/scala-pitfalls-8/)
- [scala 雾中风景(9): List(1,2,3) == Seq(1,2,3) ?](http://hongjiang.info/scala-pitfalls-9/)
- [scala 雾中风景(10): 逆变点与协变点](http://hongjiang.info/scala-pitfalls-10/)
- [scala 雾中风景(11): isInstanceOf 与类型擦拭](http://hongjiang.info/scala-pitfalls-11-type-erasure/)
- [scala 雾中风景(12): App 特质的延迟初始化](http://hongjiang.info/scala-app-trait-delay-init/)
- [scala 雾中风景(13): 模式匹配中的逻辑或](http://hongjiang.info/scala-pitfalls-13/)
- [scala 雾中风景(14): trait 的泛型参数为何不支持 context bounds](http://hongjiang.info/scala-pitfalls-14/)
- [scala 雾中风景(15): class A { type T }与 class A[T] {}](http://hongjiang.info/scala-pitfalls-15/)
- [scala 雾中风景(16): println(1,2,3)为什么 work?](http://hongjiang.info/scala-pitfalls-16/)
- [scala 雾中风景(17): toSet()的谜题](http://hongjiang.info/scala-pitfalls-17/)
- [scala 雾中风景(18): postfix operator 的问题](http://hongjiang.info/scala-pitfalls-18/)
- [scala 雾中风景(19): MutableList 与 mutable.LinkedList 的问题](http://hongjiang.info/scala-pitfalls-19/)
- [scala 雾中风景(20): MutableList 迭代器的 bug](http://hongjiang.info/scala-pitfalls-20/)
- [scala 雾中风景(21): auto-tupling 与 auto-detupling](http://hongjiang.info/scala-pitfalls-21-auto-tupling-and-auto-detupling/)
- [scala 雾中风景(22): var 变量与赋值操作符](http://hongjiang.info/scala-pitfalls-22/)
- [scala 雾中风景(23): Nothing 类型引发的 NullPointerException](http://hongjiang.info/scala-pitfalls-23-nothing-caused-npe/)
- [scala 雾中风景(24): break 与异常捕获](http://hongjiang.info/scala-pitfalls-24/)
- [scala 雾中风景(25): try-finally 表达式的类型推导](http://hongjiang.info/scala-pitfalls-25-try-finally-expr-type-infer/)
- [scala 雾中风景(26): 变量查找的问题](http://hongjiang.info/scala-pitfalls-26/)

## 诊断

- [scala 的诊断方法(1) 使用-Xprint:typer 看语法糖的背后](http://hongjiang.info/scala-diagnose-1/)
- [scala 的诊断方法(2) 在 repl 下用 reify 查看表达式的翻译结果](http://hongjiang.info/scala-diagnose-2/)
- [scala 的诊断方法(3) 在 repl 下统计方法的执行时间](http://hongjiang.info/scala-diagnose-3/)
- [scala 的诊断方法(4) -Ytyper-debug 编译项](http://hongjiang.info/scala-diagnose-4/)
- [scala 的诊断方法(5) 用 scalac-aspects 诊断 scalac 各阶段耗时](http://hongjiang.info/scalac-aspects/)

## 函数与函数式风格

- [无参方法与小括号问题](http://hongjiang.info/scala-parenthesis-and-apply/)
- [scala 中的无参方法与统一访问原则](http://hongjiang.info/scala-uniform-access-principle/)
- [scala 中的 eta-conversion](http://hongjiang.info/scala-eta-conversion/)
- [闭包变量绑定问题](http://hongjiang.info/closure-var-banding/)
- [如何写一段符合 scala 语言习惯的快速排序](http://hongjiang.info/scala-quicksort/)
- [Any.##方法与 hashCode 的区别](http://hongjiang.info/double-pound-sign-and-hashcode/)
- [scala 中的有名参数](http://hongjiang.info/scala-named-arguments/)
- [map 函数，隐式参数 CanBuildFrom 的细节](http://hongjiang.info/scala-canbuildfrom-detail/)
- [scala 中函数类型的多态](http://hongjiang.info/scala-function-polymorphic/)
- [scala 不是函数式语言，与 Ocaml 的对比](http://hongjiang.info/scala-vs-ocaml/)
- [foldLeft 与 foldRight](http://hongjiang.info/foldleft-and-foldright/)
- [再谈 eta-conversion 与 eta-expansion](http://hongjiang.info/eta-conversion-and-eta-expansion/)
- [柯里化(currying)与构造器(Builder)模式](http://hongjiang.info/currying-and-builder-pattern/)

## 集合相关

- [对 tuple 进行迭代](http://hongjiang.info/tuple-iterator/)
- [String 当作集合处理时的方法](http://hongjiang.info/string-as-collection/)
- [scala 中集合的交集、并集、差集](http://hongjiang.info/scala-union-diff-intersect/)
- [Tuple1 的存在意义？](http://hongjiang.info/tuple1-purpose/)
- [为什么 scala 中的 tuple 定义了 22 个(Tuple22)?](http://hongjiang.info/why-tuples-only-to-22/)
- [二元组箭头表达式背后的语法糖](http://hongjiang.info/scala-any2arrowassoc/)
- [通过 List.apply 方法构造 List 的背后逻辑](http://hongjiang.info/scala-list-apply/)

## API pitfalls

- [scala 类库中的 api 陷阱(1): LinkedList.append](http://hongjiang.info/scala-api-pitfalls-1/)

## REPL 相关

- [repl 杂记](http://hongjiang.info/repl-misc/)
- [repl 下的几种模式](http://hongjiang.info/scala-repl-modes/)
- [repl 下的 javap](http://hongjiang.info/scala-repl-javap/)
- [scala2.11 的 repl 下增加了 kind 命令](http://hongjiang.info/scala-repl-kind/)

## Scala 2.10+

- [scala2.10 中 eval 一段 script](http://hongjiang.info/scala210-eval-script/)
- [scala2.10.1 的 repl 下:cp 命令不能工作](http://hongjiang.info/scala210-repl-cp-do-not-work/)
- [scala2.10 中采纳了 SIP-18:模块化语言特性](http://hongjiang.info/scala-sip-18/)
- [scala2.10 里的 for 表达式已经不允许对变量声明 val](http://hongjiang.info/for-comprehension-val-definition/)
- [scala2.11 编译环节的一些变动: delambdafy](http://hongjiang.info/scala-compiler-delambdafy/)
- [scala2.11 编译器对 lint 的增强](http://hongjiang.info/scala-211-compiler-lint/)

## 未分类

- [lazy 变量与双重检测锁(DCL)](http://hongjiang.info/scala-lazy-and-dcl/)
- [scala 里的静态代理(static-forwarders)](http://hongjiang.info/scala-static-forwarders/)
- [统计诗经中最常使用的叠词](http://hongjiang.info/scala-counting%E2%80%A6ated-character/)
- [scala2.9 中@serializable 注释已不鼓励使用](http://hongjiang.info/serializable-annotation-deprecated/)
- [import <span class="underline">root</span>.xxx 中的\_root\_前缀表示 xxx 包名是绝对路径](http://hongjiang.info/scala-package-root-prefix/)
- [scala 中执行外部命令(scala.sys.process)](http://hongjiang.info/scala-process/)
- [classloader 问题：import my.package.\_ 是否会 load 该包下所有的 class?](http://hongjiang.info/classloader-question-on-import-classes/)
- [scala 中有 Unicode 的关键字](http://hongjiang.info/scala-unicode-reserved-words/)
- [Any 类的源码在哪儿？](http://hongjiang.info/cannot-find-soucecode-of-class-any/)
- [scala 编译器的一个 bug](http://hongjiang.info/scala-compiler-bug/)
- [scala bug 系列：2.10 编译器把单例当作类型的 bug](http://hongjiang.info/scala-bug-210-object-as-type/)
- [scala 里模拟 javascript/python 里的生成器的效果](http://hongjiang.info/scala-simulate-javascript-generator/)
- [null 造型为值类型时为何不抛异常](http://hongjiang.info/null-cast-to-value-type/)
- [Int 与 Integer 的拆箱问题](http://hongjiang.info/scala-int-unbox-for-null/)
- [Scala 函数式编程中文版已上架](http://hongjiang.info/functional-programming-in-scala-chinese-version/)
- [scalastyle 工具](http://hongjiang.info/scala-style-checker/)

## 分享与交流

- [分享 ppt: scala 中的函数与闭包](http://hongjiang.info/scala-function-and-closure/)
- [与 19 楼的交流](http://hongjiang.info/scala-19lou/)
- [上海 scala 爱好者聚会(2013)](http://hongjiang.info/scala-shanghai-512/)
- [阿里技术嘉年华 2013](http://hongjiang.info/adc2013/)
- [2013 华东 scala 爱好者聚会(杭州)](http://hongjiang.info/scala-hangzhou-2013-1019/)
- [华东地区 scala 爱好者聚会(2014 上海)](http://hongjiang.info/scala-shanghai-2014/)
- [华东地区 scala 爱好者聚会(2015 上海)](http://hongjiang.info/scala-shanghai-2015/)
- [Scala 在挖财的应用实践](http://hongjiang.info/scala-in-wacai/)
- [ArchSummit 北京 2015 小记](http://hongjiang.info/archsummit-beijing-2015/)

## 依赖注入

- [Cake Pattern 与依赖注入](http://hongjiang.info/cake-pattern-and-di/)
- [scala 中的 self type(自身类型)与依赖注入](http://hongjiang.info/scala-self-type-and-di/)
