# 在 Java 中反转并行流的元素

> 原文:[https://www . geesforgeks . org/reverse-of-a-parallel-stream-in-Java/](https://www.geeksforgeeks.org/reverse-elements-of-a-parallel-stream-in-java/)

给定一个 Java 中的并行流，任务是反转它的元素。

**示例:**

```java
Input: Parallel Stream = {11, 22, 33, 44}
Output: {44, 33, 22, 11}

Input: Parallel Stream = {a, b, c, d}
Output: {d, c, b, a}

```

以下是各种方法:

1.  **[使用 Collectors 类](https://www.geeksforgeeks.org/collections-sort-java-examples/) :** 由于 Java 中的 Streams 不存储任何元素，因此在 Collectors 类的帮助下，使用一个中间集合来创建一个新的 stream。
    **算法:**

1.  获取并行流。
2.  使用 Collectors.toList()方法将流转换为列表。
3.  对于此列表，使用 Collections.reverse()方法反转其元素。
4.  使用 List.stream()方法将此反向列表转换为流。
5.  返回/打印此流，元素反转。

下面是上述方法的实现:

**程序:**

```java
// Java program to reverse elements
// of a parallel Stream

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to reverse
    // the elements of the parallel stream
    public static <T> Collector<T, ?, Stream<T> > reverseStream()
    {
        return Collectors
            .collectingAndThen(Collectors.toList(),
                               list -> {
                                   Collections.reverse(list);
                                   return list.stream();
                               });
    }

    // Driver code
    public static void main(String[] args)
    {

        // Get the parallel stream
        List<Integer> lists = Arrays.asList(11, 22, 33, 44);
        Stream<Integer> stream = lists.parallelStream();

        // Reverse and print the elements
        stream.collect(reverseStream())
            .forEach(System.out::println);
    }
}
```

**Output:**

```java
44
33
22
11

```

*   **Using [LinkedList class](https://www.geeksforgeeks.org/linked-list-in-java/) :** LinkedList class implements List interface and has a feature called Stack. So LinkedList supports insertion at the front. Taking advantage of this, a LinkedList can be created from elements of the specified stream and return descending iterator to it. This would reverse the elements of the parallel stream.

    **算法:**

    1.  获取并行流。
    2.  使用 Collectors.toCollection()方法将流转换为 LinkedList。
    3.  对于这个链接列表，使用 descendingIterator()方法返回降序迭代器。
    4.  返回/打印元素反转的迭代器。

    下面是上述方法的实现:

    **程序:**

    ```java
    // Java program to reverse elements
    // of a parallel Stream

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to reverse
        // the elements of the parallel stream
        public static <T> Iterator<T> reverseStream(Stream<T> stream)
        {
            return stream
                .collect(Collectors
                             .toCollection(LinkedList::new))
                .descendingIterator();
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the parallel stream
            List<Integer> lists = Arrays.asList(11, 22, 33, 44);
            Stream<Integer> stream = lists.parallelStream();

            // Reverse and print the elements
            Iterator<Integer> reverse = reverseStream(stream);
            reverse.forEachRemaining(System.out::println);
        }
    }
    ```

    **Output:**

    ```java
    44
    33
    22
    11

    ```

    *   **Collector.of() :** The idea is to create a collector that accumulates elements of the specified Stream into an ArrayDeque or ArrayList in reverse order

    **算法:**

    1.  获取并行流。
    2.  使用 Collectors.of()方法将流转换为集合。
    3.  在这个集合中，以相反的顺序添加元素
    4.  使用 Collection.stream()方法将此反向集合转换为流。
    5.  返回/打印此流，元素反转。

    下面是上述方法的实现:

    **程序:**

    ```java
    // Java program to reverse elements
    // of a parallel Stream

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to reverse
        // the elements of the parallel stream
        public static <T> Stream<T> reverseStream(Stream<T> stream)
        {
            return stream
                .collect(
                    Collector.of(
                        () -> new ArrayDeque<T>(), ArrayDeque::addFirst, (a, b) -> {
                            b.addAll(a);
                            return b;
                        }))
                .stream();
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the parallel stream
            List<Integer> lists = Arrays.asList(11, 22, 33, 44);
            Stream<Integer> stream = lists.parallelStream();

            // Reverse and print the elements
            reverseStream(stream)
                .forEach(System.out::println);
        }
    }
    ```

    **Output:**

    ```java
    44
    33
    22
    11

    ```