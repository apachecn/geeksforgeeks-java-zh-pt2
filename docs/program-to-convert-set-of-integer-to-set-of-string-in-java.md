# 用 Java 将整数集转换成字符串集的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-set-of-to-set-of-of-string-in-Java/](https://www.geeksforgeeks.org/program-to-convert-set-of-integer-to-set-of-string-in-java/)

[Java Set](https://www.geeksforgeeks.org/set-in-java/) 是 java.util 包的一部分，扩展了 java.util.Collection 接口。它不允许使用重复元素，最多只能容纳一个空元素。

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。Java 8 Stream API 可用于将**设置<integer>转换为<string>设置</string></integer>T6。**

**算法**:

1.  获取整数集。
2.  将整数集转换为整数流。这是使用 Set.stream()完成的。
3.  将整数流转换为字符串流。这是使用 Stream.map()完成的。
4.  将字符串流收集到字符串集中。这是使用 Collectors.toSet()完成的。
5.  返回/打印字符串集。

**程序 1:** 使用直接转换。

```java
// Java Program to convert
// Set<Integer> to Set<String> in Java 8

import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String args[])
    {
        // Create a set of integers
        Set<Integer> setOfInteger = new HashSet<>(
            Arrays.asList(1, 2, 3, 4, 5));

        // Print the set of Integer
        System.out.println("Set of Integer: " + setOfInteger);

        // Convert Set of integers to set of String
        Set<String> setOfString = setOfInteger.stream()
                                      .map(String::valueOf)
                                      .collect(Collectors.toSet());

        // Print the set of String
        System.out.println("Set of String: " + setOfString);
    }
}
```

**Output:**

```java
Set of Integer: [1, 2, 3, 4, 5]
Set of String: [1, 2, 3, 4, 5]

```

**程序 2:** 使用泛型函数。

```java
// Java Program to convert
// Set<Integer> to Set<String> in Java 8

import java.util.*;
import java.util.stream.*;
import java.util.function.Function;

class GFG {

    // Generic function to convert Set of 
    // Integer to Set of String
    public static <T, U> Set<U>
    convertIntSetToStringSet(Set<T> setOfInteger, 
                          Function<T, U> function)
    {
        return setOfInteger.stream()
            .map(function)
            .collect(Collectors.toSet());
    }

    public static void main(String args[])
    {

        // Create a set of integers
        Set<Integer> setOfInteger = new HashSet<>(
            Arrays.asList(1, 2, 3, 4, 5));

        // Print the set of Integer
        System.out.println("Set of Integer: " + setOfInteger);

        // Convert Set of integers to set of String
        Set<String> setOfString = convertIntSetToStringSet(
                                                      setOfInteger,
                                                      String::valueOf);

        // Print the set of String
        System.out.println("Set of String: " + setOfString);
    }
}
```

**Output:**

```java
Set of Integer: [1, 2, 3, 4, 5]
Set of String: [1, 2, 3, 4, 5]

```