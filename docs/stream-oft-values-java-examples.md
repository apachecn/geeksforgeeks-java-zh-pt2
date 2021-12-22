# Java 中的(T…值)流，示例

> 原文:[https://www . geesforgeks . org/stream-oft-values-Java-examples/](https://www.geeksforgeeks.org/stream-oft-values-java-examples/)

**流(T…值)**返回一个顺序的有序流，其元素是指定的值。顺序流就像使用单核的 for 循环一样工作。另一方面，并行流利用计算机的多个内核，将所提供的任务分成许多部分，并在不同的线程中运行。

**语法:**

```
static <**T**> Stream<**T**> of(T... values)

Where, Stream is an interface and T
is the type of stream elements.
values represents the elements of the 
new stream and the function 
returns the new stream.

```

**示例 1 :** 字符串流。

```
// Java code for Stream.of()
// to get sequential ordered stream
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream of Strings
        // and printing sequential
        // ordered stream
        Stream<String> stream = Stream.of("Geeks", "for", "Geeks");

        stream.forEach(System.out::println);
    }
}
```

输出:

```
Geeks
for
Geeks

```

**示例 2 :** 整数流。

```
// Java code for Stream.of()
// to get sequential ordered stream
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream of Integer
        // and printing sequential
        // ordered stream
        Stream<Integer> stream = Stream.of(5, 7, 9, 12);

        stream.forEach(System.out::println);
    }
}
```

输出:

```
5
7
9
12

```

**例 3 :** 长基元流。

```
// Java code for Stream.of()
// to get sequential ordered stream
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream of Long
        // and printing sequential
        // ordered stream
        Stream<Long> stream = Stream.of(4L, 8L, 12L, 16L, 20L);

        stream.forEach(System.out::println);
    }
}
```

输出:

```
4
8
12
16
20

```