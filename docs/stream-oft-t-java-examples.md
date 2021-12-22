# Java 中的(T . T)流，带示例

> 原文:[https://www.geeksforgeeks.org/stream-oft-t-java-examples/](https://www.geeksforgeeks.org/stream-oft-t-java-examples/)

**(T)的流**返回包含单个元素的顺序流，即单个顺序流。顺序流就像使用单核的 for 循环一样工作。另一方面，并行流利用计算机的多个内核，将所提供的任务分成许多部分，并在不同的线程中运行。

**语法:**

```
static <**T**> Stream<**T**> of(**T** t)

Where, Stream is an interface and T
is the type of stream elements.
t is the single element and the
function returns a singleton 
sequential stream.

```

**示例 1 :** 单例字符串流。

```
// Java code for Stream.of()
// to get sequential Stream
// containing a single element.
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream of Strings
        // and printing sequential Stream
        // containing a single element
        Stream<String> stream = Stream.of("Geeks");

        stream.forEach(System.out::println);
    }
}
```

输出:

```
Geeks

```

**示例 2 :** 单例整数流。

```
// Java code for Stream.of()
// to get sequential Stream
// containing a single element.
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream of Integer
        // and printing sequential Stream
        // containing a single element
        Stream<Integer> stream = Stream.of(5);

        stream.forEach(System.out::println);
    }
}
```

输出:

```
5

```

**例 3 :** 单例长流。

```
// Java code for Stream.of()
// to get sequential Stream
// containing a single element.
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream of Long
        // and printing sequential Stream
        // containing a single element
        Stream<Long> stream = Stream.of(4L);

        stream.forEach(System.out::println);
    }
}
```

输出:

```
4

```