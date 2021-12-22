# 用 Java 将列表转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-list-to-stream-in-Java/](https://www.geeksforgeeks.org/program-to-convert-list-to-stream-in-java/)

[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)是收藏的子界面。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。列表接口由[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)、[链表](https://www.geeksforgeeks.org/linked-list-in-java/)、[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)和[栈](https://www.geeksforgeeks.org/stack-class-in-java/)类实现。

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。

下面是用 Java 将列表转换为流的各种方法:

1.  **Using List.stream() method**: Java List interface provides stream() method which returns a sequential Stream with this collection as its source.

    **语法:**

    ```
    List.stream()
    ```

    **算法**:

    1.  获取流
    2.  使用 List.stream()方法将流转换为列表。
    3.  返回列表

    **程序:**

    ```
    // Java Program to convert
    // List to Stream in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.Function;

    class GFG {

        // Generic function to convert a list to stream
        private static <T> Stream<T> convertListToStream(List<T> list)
        {
            return list.stream();
        }

        public static void main(String args[])
        {

            // Create a stream of integers
            List<String> list = Arrays.asList("GeeksForGeeks",
                                              "A computer portal", 
                                              "for Geeks");

            // Print the List
            System.out.println("List: " + list);

            // Convert List to stream
            Stream<String> stream = convertListToStream(list);

            // Print the Stream
            System.out.println("Stream from List: "
                        + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    List: [GeeksForGeeks, A computer portal, for Geeks]
    Stream from List: [GeeksForGeeks, A computer portal, for Geeks]

    ```

2.  **Filter Stream using a Predicate**: The **[Functional Interface Predicate](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)** is defined in the java.util.Function package and can therefore be used as the assignment target for a lambda expression or method reference. It improves manageability of code, helps in unit-testing them separately

    **算法**:

    1.  获取流
    2.  通过使用预定义的静态方法或通过重写谓词接口创建新方法来定义谓词条件。在这个程序中，接口被覆盖以匹配以“G”开头的字符串。
    3.  使用 List.stream()方法将流转换为列表。
    4.  使用定义的谓词条件过滤获得的流
    5.  已获得所需的流。
        因此，使用 forEach()方法打印流的过滤元素。
        也可以根据需要退货。

    **程序:**

    ```
    // Java Program to convert
    // List to Stream in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.*;

    class GFG {

        public static void main(String args[])
        {

            // Create a stream of integers
            List<String> list = Arrays.asList("GeeksForGeeks",
                                              "A computer portal", 
                                              "for", 
                                              "Geeks");

            // Print the List
            System.out.println("List: " + list);

            // Create the predicate for item starting with G
            Predicate<String> predicate = new Predicate<String>() {
                @Override
                public boolean test(String s)
                {
                    // filter items that start with "G"
                    return s.startsWith("G");
                }
            };

            System.out.println("Stream from List with items"+
                                          " starting with G: ");

            // Convert List to stream
            list.stream()
                .filter(predicate)
                .forEach(System.out::println);
        }
    }
    ```

    **Output:**

    ```
    List: [GeeksForGeeks, A computer portal, for, Geeks]
    Stream from List with items starting with G: 
    GeeksForGeeks
    Geeks

    ```