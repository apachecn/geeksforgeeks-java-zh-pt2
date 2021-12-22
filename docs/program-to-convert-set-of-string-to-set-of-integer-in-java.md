# 在 Java 中将字符串集合转换为整数集合的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-set-of-to-set-of-integer-in-Java/](https://www.geeksforgeeks.org/program-to-convert-set-of-string-to-set-of-integer-in-java/)

[Java Set](https://www.geeksforgeeks.org/set-in-java/) 是 java.util 包的一部分，扩展了 java.util.Collection 接口。它不允许使用重复元素，最多只能容纳一个空元素。

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。Java 8 Stream API 可用于将**设置<integer>转换为<string>设置</string></integer>T6。**

**算法**:

1.  获取字符串的集合。
2.  将字符串集转换为字符串流。这是使用 Set.stream()完成的。
3.  将字符串流转换为整数流。这是通过使用 Stream.map()并将 Integer.parseInt()方法作为 lambda 表达式传递来完成的。
4.  将整数流收集到整数集中。这是使用 Collectors.toSet()完成的。
5.  返回/打印字符串集。

**程序 1:** 使用直接转换。

```java
// Java Program to convert
// Set<String> to Set<Integer> in Java 8

import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String args[])
    {
        // Create a set of String
        Set<String> setOfString = new HashSet<>(
            Arrays.asList("1", "2", "3", "4", "5"));

        // Print the set of String
        System.out.println("Set of String: " + setOfString);

        // Convert Set of String to set of Integer
        Set<Integer> setOfInteger = setOfString.stream()
                                        .map(s -> Integer.parseInt(s))
                                        .collect(Collectors.toSet());

        // Print the set of Integer
        System.out.println("Set of Integer: " + setOfInteger);
    }
}
```

**Output:**

```java
Set of String: [1, 2, 3, 4, 5]
Set of Integer: [1, 2, 3, 4, 5]

```

**程序 2:** 使用泛型函数。

```java
// Java Program to convert
// Set<String> to Set<Integer> in Java 8

import java.util.*;
import java.util.stream.*;
import java.util.function.Function;

class GFG {

    // Generic function to convert Set of
    // String to Set of Integer
    public static <T, U> Set<U>
    convertStringSetToIntSet(Set<T> setOfString,
                             Function<T, U> function)
    {
        return setOfString.stream()
            .map(function)
            .collect(Collectors.toSet());
    }

    public static void main(String args[])
    {

        // Create a set of String
        Set<String> setOfString = new HashSet<>(
            Arrays.asList("1", "2", "3", "4", "5"));

        // Print the set of String
        System.out.println("Set of String: " + setOfString);

        // Convert Set of String to set of Integer
        Set<Integer> setOfInteger = convertStringSetToIntSet(
            setOfString,
            Integer::parseInt);

        // Print the set of Integer
        System.out.println("Set of Integer: " + setOfInteger);
    }
}
```

**Output:**

```java
Set of String: [1, 2, 3, 4, 5]
Set of Integer: [1, 2, 3, 4, 5]

```