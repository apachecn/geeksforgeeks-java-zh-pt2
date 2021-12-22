# Java 中的 Stream forEach()方法，带示例

> 原文:[https://www . geesforgeks . org/stream-foreach-method-Java-examples/](https://www.geeksforgeeks.org/stream-foreach-method-java-examples/)

**流 forEach(消费者动作)**为流的每个元素执行一个动作。流 forEach(消费者行为)是一种 ***终端操作*** ，也就是说，它可能穿越流以产生结果或副作用。

**语法:**

```java
void forEach(Consumer<**?** super T> action)

Where, Consumer is a functional interface
and T is the type of stream elements.

```

**注意:**这个操作的行为是显式不确定的。此外，对于任何给定的元素，动作可以在库选择的任何时间和任何线程中执行。

**例 1 :** 对反向排序流的每个元素进行打印操作。

```java
// Java code for forEach
// (Consumer action) in Java 8
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Integers
        List<Integer> list = Arrays.asList(2, 4, 6, 8, 10);

        // Using forEach(Consumer action) to
        // print the elements of stream
        // in reverse order
        list.stream().sorted(Comparator.reverseOrder()).forEach(System.out::println);
    }
}
```

**Output:**

```java
10
8
6
4
2

```

**例 2 :** 对字符串流的每个元素进行打印操作。

```java
// Java code for forEach
// (Consumer action) in Java 8
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("GFG", "Geeks",
                                          "for", "GeeksforGeeks");

        // Using forEach(Consumer action) to
        // print the elements of stream
        list.stream().forEach(System.out::println);
    }
}
```

**Output:**

```java
GFG
Geeks
for
GeeksforGeeks

```

**例 3 :** 对反向排序后的字符串流的每个元素进行打印操作。

```java
// Java code for forEach
// (Consumer action) in Java 8
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a Stream of Strings
        Stream<String> stream = Stream.of("GFG", "Geeks",
                                          "for", "GeeksforGeeks");

        // Using forEach(Consumer action) to print
        // Character at index 1 in reverse order
        stream.sorted(Comparator.reverseOrder())
            .flatMap(str -> Stream.of(str.charAt(1)))
            .forEach(System.out::println);
    }
}
```

**Output:**

```java
o
e
e
F

```