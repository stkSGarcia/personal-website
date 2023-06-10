---
title: "[Java] Splitting a comma-separated string but ignoring commas in quotes"
authors:
  - Shenghui Gu
date: 2018-03-24T21:04:00+08:00
lastmod: 2021-08-24T23:12:34+08:00
tags:
  - RegEx
  - Java
---

Sometimes we need to parse strings like this:

```text
"1234567890","James",man,"New York, NY, USA"
```

And the output we need is as follows:

```text
"1234567890"
"James"
man
"New York, NY, USA"
```

<!-- more -->

We can try the following code:

```java
String line = "\"1234567890\",\"James\",man,\"New York, NY, USA\"";
String[] tokens = line.split(",(?=(?:[^\"]*\"[^\"]*\")*[^\"]*$)", -1);
Arrays.stream(tokens).forEach(System.out::println);
```

In other words: split on the comma only if that comma has zero, or an even number of quotes ahead of it.

A bit friendlier for the eyes:

```java
String line = "\"1234567890\",\"James\",man,\"New York, NY, USA\"";

String otherThanQuote = " [^\"] ";
String quotedString = String.format(" \" %s* \" ", otherThanQuote);
String regex = String.format("(?x) "+ // enable comments, ignore white spaces
                             ",                         "+ // match a comma
                             "(?=                       "+ // start positive look ahead
                             "  (?:                     "+ //   start non-capturing group 1
                             "    %s*                   "+ //     match 'otherThanQuote' zero or more times
                             "    %s                    "+ //     match 'quotedString'
                             "  )*                      "+ //   end group 1 and repeat it zero or more times
                             "  %s*                     "+ //   match 'otherThanQuote'
                             "  $                       "+ // match the end of the string
                             ")                         ", // stop positive look ahead
                             otherThanQuote, quotedString, otherThanQuote);

String[] tokens = line.split(regex, -1);
Arrays.stream(tokens).forEach(System.out::println);
```

About `split(String regex, int limit)` method.

The _limit_ parameter controls the number of times the pattern is applied and therefore affects the length of the resulting array.

- If the _limit_ `n` is **greater than zero** then the pattern will be applied at most `n - 1` times, the array's length will be no greater than `n`, and the array's last entry will contain all input beyond the last matched delimiter.
- If `n` is **non-positive** then the pattern will be applied as many times as possible and the array can have any length.
- If `n` is **zero** then the pattern will be applied as many times as possible, the array can have any length, and trailing empty strings will be discarded.

The string "boo:and:foo", for example, yields the following results with these parameters:

| Regex | Limit | Result                        |
| ----- | ----- | ----------------------------- |
| :     | 2     | { "boo", "and:foo" }          |
| :     | 5     | { "boo", "and", "foo" }       |
| :     | -2    | { "boo", "and", "foo" }       |
| o     | 5     | { "b", "", ":and:f", "", "" } |
| o     | -2    | { "b", "", ":and:f", "", "" } |
| o     | 0     | { "b", "", ":and:f" }         |

> - [Stack Overflow](https://stackoverflow.com/questions/1757065)
> - [Java Doc](<https://docs.oracle.com/javase/6/docs/api/java/lang/String.html#split(java.lang.String,%20int)>)
