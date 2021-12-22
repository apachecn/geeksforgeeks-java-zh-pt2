# 使用番石榴的收集器收集流到 Java 中的不可变集合

> 原文:[https://www . geeksforgeeks . org/using-guavas-collectors-for-collection-streams-to-不可变-collections-in-java/](https://www.geeksforgeeks.org/using-guavas-collectors-for-collecting-streams-to-immutable-collections-in-java/)

番石榴是谷歌的一组核心库，包括新的收藏类型。例如，我们有多映射和多集合、不可变集合、图形库和并发实用程序。它被许多公司使用。在本文中，我们将看到如何在 Java 中使用番石榴的收集器来收集流到不可变的集合。要使用番石榴，我们需要添加 [Maven 依赖。](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html)否则，我们必须从外部将这个库添加到我们的项目中。

插图:

```
<dependency>
          <groupId>com.google.guava</groupId>
          <artifactId>guava</artifactId>
          <version>22.0</version>
</dependency>
```

为了便于理解，在跳到实现之前，让我们先回顾一下涉及方法的同样重要的概念。流的[概念](https://www.geeksforgeeks.org/stream-in-java/)在这里起着主要作用，这在 Java 8 中已经介绍过了。流表示一系列元素，并支持不同类型的操作来对这些元素执行计算或批量操作。

*   流不是数据结构，而是从集合、数组或输入/输出通道获取输入。
*   流不改变原始的数据结构，它们只根据流水线方法提供结果。
*   每个中间操作都被延迟执行，并作为结果返回一个流，因此各种中间操作可以被流水线化。终端操作标记流的结尾并返回结果。

**语法:**

```
static IntStream range (int start, int end)
```

**返回类型**:整数流

**说明**:此方法用于返回整数流的顺序

```
Stream intStream boxed()
```

**返回类型**:流

**描述**:这个方法返回由这个流的元素组成的流

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Use Guava's Collectors
// for Collecting Streams to Immutable Collections

// Importing utility classes from java.util package
// Importing guava Library
import com.google.common.collect.ImmutableList;
import java.util.ArrayList;
import java.util.List;
import java.util.stream.IntStream;

// Main class
public class App {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a stream of Integers from 0 to 9
        // by using boxed method coverting that stream
        // into stream of elements
        List<Integer> list
            = IntStream.range(0, 9).boxed().collect(
                ImmutableList.toImmutableList());
        // printing the list
        System.out.println(list);
    }
}
```

**输出:**

```
[0, 1, 2, 3, 4, 5, 6, 7, 8]
```

> **注意:**在上面的输出中，我们已经打印了一个不可变的整数列表。如果我们试图修改列表，它将抛出一个[不支持操作异常](https://www.geeksforgeeks.org/how-to-solve-java-list-unsupportedoperationexception/)。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Use Guava's Collectors
// for Collecting Streams to Immutable Collections
// Where UnsupportedOperationException is thrown

// Importing utility classes from java.util package
// Importing Guava library
import com.google.common.collect.ImmutableList;
import java.util.ArrayList;
import java.util.List;
import java.util.stream.IntStream;

// Main class
public class App {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a stream of Integers from 0 to 9
        // by using boxed method coverting that stream
        // into stream of elements
        List<Integer> list
            = IntStream.range(0, 9).boxed().collect(
                ImmutableList.toImmutableList());

        // Adding more elements to immutatble list
        // Note: Trying to add
        list.add(12);
        list.add(13);
        list.add(14);

        // Print and display the List
        System.out.println(list);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.UnsupportedOperationException
at com.google.common.collect.ImmutableCollection.add(ImmutableCollection.java:220)
at james.App.main(App.java:15)
```