+++
title = "用遗传算法求解 N 皇后问题"
author = "Samuel Garcia"
date = 2018-03-11T00:07:00+08:00
lastmod = 2021-08-24T23:12:33+08:00
tags = ["genetic-algorithm"]
+++

## N 皇后问题

首先介绍八皇后问题。八皇后问题是一个以国际象棋为背景的问题：如何能够在 `8×8` 的国际象棋棋盘上放置八个皇后，使得任何一个皇后都无法直接吃掉其他的皇后？
为了达到此目的，任两个皇后都不能处于同一条横行、纵行或斜线上。

八皇后问题可以推广为更一般的 N 皇后摆放问题：这时棋盘的大小变为 `N×N` 。

<!--more-->

## 遗传算法

遗传算法（Genetic Algorithm, GA）是借鉴生物界自然选择和自然遗传机制的启发式搜索算法。
它模拟一个人工种群的进化过程，通过选择、交叉以及变异等机制，在每次迭代中都保留一组候选个体，重复此过程，种群经过若干代进化后，理想情况下其适应度达到近似最优的状态。

### 算法过程

总结一下是下列几个步骤：

1. 初始化种群（Initial population）
2. 计算适应度（Fitness function）
3. 选择（Selection）
4. 交叉（Crossover）
5. 变异（Mutation）

用伪代码来描述就是：

```text
START
Generate the initial population
Compute fitness
REPEAT
    Selection
    Crossover
    Mutation
    Compute fitness
UNTIL population has converged
STOP
```

### 编码与解码

实现遗传算法的第一步就是明确对求解问题的编码和解码方式。

一般有两种编码方式，各具优缺点：

- 实数编码：直接用实数表示基因，容易理解且不需要解码过程，但容易过早收敛，从而陷入局部最优。
- 二进制编码：稳定性高，种群多样性大，但需要的存储空间大，需要解码且难以理解。

在本问题中可以采用实数编码，例如，当 `N = 8` 时，其中一个编码可以是 `78563412` ，其中每一个数字的位置代表皇后在棋盘上的行数，每一个值代表皇后在当前行中所出列的位置。
比如 `6` 代表该皇后在棋盘的第 4 行第 6 列。

### 个体与种群

“染色体”表达了某种特征，这种特征的载体，称为“个体”。
许多这样的个体组成了一个种群。

### 适应度函数

遗传算法中，一个个体（解）的好坏用适应度函数值来评价。
在本问题中，有多少皇后满足要求就是适应度函数。

适应度函数值越大，解的质量越高。
适应度函数是遗传算法进化的驱动力，也是进行自然选择的唯一标准，它的设计应结合求解问题本身的要求而定。

### 选择

选择操作是从前代种群中选择多对较优个体，一对较优个体称之为一对父母，让父母们将它们的基因传递到下一代，直到下一代个体数量达到种群数量上限。

在选择操作前，将种群中个体按照适应度从小到大进行排列。

采用轮盘赌选择方法（当然还有很多别的选择方法），各个个体被选中的概率与其适应度函数值大小成正比。
轮盘赌选择方法具有随机性，在选择的过程中可能会丢掉较好的个体，所以可以使用精英机制，将前代最优个体直接选择。

在本问题中，直接将适应度最高的两个个体作为父母。

### 交叉

两个待交叉的不同的染色体（父母）根据交叉概率按某种方式交换其部分基因。
一般来说交叉概率比较大。

可以采用单点交叉法，也可以使用其他交叉方法，应根据实际情况定义合适的交叉算法。

### 变异

染色体按照变异概率进行染色体的变异。一般来说变异概率比较小。

可以采用单点变异法，也可以使用其他变异方法。

## Java 实现

```java
import java.util.*;
import java.util.stream.Collectors;

public class Queen {
    private static int N = 10;
    private static double RATE = 0.3;

    public static void main(String[] args) {
        Queen queen = new Queen();
        HashSet<String> result = new HashSet<>();
        int[] father = queen.init();
        int[] mother = queen.init();
        int times = 3000000;
        for (int i = 0; i < times; i++) {
            List<Integer[]> son = new ArrayList<>();
            for (int j = 0; j < N; j++) {
                son.add(Arrays.stream(queen.crossover(father, mother)).boxed().toArray(Integer[]::new));
            }
            son = queen.mutation(son);
            Map<Integer[], Integer> res = queen.selection(son);
            for (Map.Entry<Integer[], Integer> c : res.entrySet()) {
                if (c.getValue() == 0) result.add(Arrays.toString(c.getKey()));
            }
            father = Arrays.stream(res.entrySet().iterator().next().getKey()).mapToInt(k -> k).toArray();
            mother = Arrays.stream(res.entrySet().iterator().next().getKey()).mapToInt(k -> k).toArray();
        }
        System.out.println("Solutions: " + result.size());
    }

    private int[] init() {
        List<Integer> list = new ArrayList<>();
        for (int i = 1; i <= N; i++) list.add(i);
        Collections.shuffle(list);
        return list.stream().mapToInt(i -> i).toArray();
    }

    private int[] crossover(int[] originFather, int[] originMother) {
        int[] father = Arrays.copyOf(originFather, N);
        int[] mother = Arrays.copyOf(originMother, N);
        int[] rend = new int[N];
        for (int i = 0; i < N; i++) {
            rend[i] = Math.random() >= 0.5 ? 0 : 1;
        }
        int[] son = new int[N];
        int f = 0, m = 0;
        for (int i = 0; i < N; i++) {
            if (rend[i] == 0) {
                for (f = 0; f < N; f++) if (father[f] != 0) break;
            } else {
                for (m = 0; m < N; m++) if (mother[m] != 0) break;
            }
            son[i] = rend[i] == 0 ? father[f] : mother[m];
            for (int j = 0; j < N; j++) {
                if (father[j] == son[i]) father[j] = 0;
                if (mother[j] == son[i]) mother[j] = 0;
            }
        }
        return son;
    }

    private List<Integer[]> mutation(List<Integer[]> chromosomes) {
        for (Integer[] chromosome : chromosomes) {
            if (Math.random() < RATE) continue;
            int i = (int) (Math.random() * N);
            int j = (int) (Math.random() * N);
            if (i == j) continue;
            chromosome[i] ^= chromosome[j];
            chromosome[j] ^= chromosome[i];
            chromosome[i] ^= chromosome[j];
        }
        return chromosomes;
    }

    private Integer fitness(Integer[] result) {
        int res = 0;
        for (int i = 0; i < N; i++) {
            for (int j = i + 1; j < N; j++) {
                if (Math.abs(result[i] - result[j]) == j - i) res++;
            }
        }
        return res;
    }

    private Map<Integer[], Integer> selection(List<Integer[]> son) {
        Map<Integer[], Integer> result = son.stream().collect(Collectors.toMap(x -> x, this::fitness));
        result = result.entrySet().stream().sorted(Map.Entry.comparingByValue()).collect(Collectors.toMap(Map.Entry::getKey, Map.Entry::getValue, (oldValue, newValue) -> oldValue, LinkedHashMap::new));
        return result;
    }
}
```

## N 皇后解的个数

| N   | Solutions        |
| --- | ---------------- |
| 1   | 1                |
| 2   | 0                |
| 3   | 0                |
| 4   | 2                |
| 5   | 10               |
| 6   | 4                |
| 7   | 40               |
| 8   | 92               |
| 9   | 352              |
| 10  | 724              |
| 11  | 2680             |
| 12  | 14200            |
| 13  | 73712            |
| 14  | 365596           |
| 15  | 2279184          |
| 16  | 14772512         |
| 17  | 95815104         |
| 18  | 666090624        |
| 19  | 4968057848       |
| 20  | 39029188884      |
| 21  | 314666222712     |
| 22  | 2691008701644    |
| 23  | 24233937684440   |
| 24  | 227514171973736  |
| 25  | 2207893435808352 |

> - [知乎 - 如何通俗易懂地解释遗传算法？有什么例子？](https://www.zhihu.com/question/23293449)
