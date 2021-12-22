# 在 Java 8 中用索引迭代流的程序

> 原文:[https://www . geesforgeks . org/program-to-iterate-over-a-stream-with-indexes-in-Java-8/](https://www.geeksforgeeks.org/program-to-iterate-over-a-stream-with-indices-in-java-8/)

给定一个 Java 中的流，任务是在索引的帮助下迭代它。

**示例:**

> **输入**:流=【G，e，e，k，s】
> **输出**:【0->G，1 - > e，2 - > e，3 - > k，4 - > s】
> 
> **输入**:流=【G，e，e，k，s，F，o，r，G，e，e，k，s】
> **输出**:【0->G，1 - > e，2 - > e，3 - > k，4 - > s，5 - > F，6 - > o，7 - > r，8 - > G，9 - > e，10

*   **方法 1:** 使用 IntStream。

    ```java
    // Java program to iterate over Stream with Indices

    import java.util.stream.IntStream;

    class GFG {
        public static void main(String[] args)
        {

            String[] array = { "G", "e", "e", "k", "s" };

            // Iterate over the Stream with indices
            IntStream

                // Get the Stream from the array
                .range(0, array.length)

                // Map each elements of the stream
                // with an index associated with it
                .mapToObj(index -> String.format("%d -> %s", 
                                           index, array[index]))

                // Print the elements with indices
                .forEach(System.out::println);
        }
    }
    ```

    **输出:**

    ```java
    0 -> G
    1 -> e
    2 -> e
    3 -> k
    4 -> s

    ```

    1.  使用 range()方法从数组中获取流。
    2.  使用 mapToObj()方法将流的每个元素映射到与之关联的索引
    3.  打印带有索引的元素
*   **方法二:**使用原子整合器。

    ```java
    // Java program to iterate over Stream with Indices

    import java.util.stream.IntStream;
    import java.util.*;
    import java.util.concurrent.atomic.AtomicInteger;

    class GFG {
        public static void main(String[] args)
        {

            String[] array = { "G", "e", "e", "k", "s" };

            // Create an AtomicInteger for index
            AtomicInteger index = new AtomicInteger();

            // Iterate over the Stream with indices
            Arrays

                // Get the Stream from the array
                .stream(array)

                // Map each elements of the stream
                // with an index associated with it
                .map(str -> index.getAndIncrement() + " -> " + str)

                // Print the elements with indices
                .forEach(System.out::println);
        }
    }
    ```

    **输出:**

    ```java
    0 -> G
    1 -> e
    2 -> e
    3 -> k
    4 -> s

    ```

    1.  为索引创建一个 AtomicInteger。
    2.  使用 Arrays.stream()方法从数组中获取流。
    3.  使用 Map()方法将流的每个元素与一个与之关联的索引进行映射，其中索引是通过每次在 getAndIncrement()方法的帮助下自动递增索引来从原子索引提取的。
    4.  打印带有索引的元素。