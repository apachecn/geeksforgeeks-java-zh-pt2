# 使用泛型将 Java 中的集合转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-a-set-to-stream-in-Java-use-generics/](https://www.geeksforgeeks.org/program-to-convert-a-set-to-stream-in-java-using-generics/)

[Java Set](https://www.geeksforgeeks.org/set-in-java/) 是 java.util 包的一部分，扩展了 java.util.Collection 接口。它不允许使用重复元素，最多只能容纳一个空元素。

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。

以下是将**设置转换为**流的各种方法。

1.  **Using Collection.stream()**: This method involves directly converting the Set to Stream using Collection.stream() method.

    **算法**:

    1.  获取要转换的集合。
    2.  将集合转换为流。这是使用 Set.stream()完成的。
    3.  返回/打印流。

    ```
    // Java Program to convert
    // Set to Stream in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.*;

    class GFG {

        // Generic function to convert a set to stream
        private static <T> Stream<T> convertSetToStream(Set<T> set)
        {
            return set.stream();
        }

        // Main method
        public static void main(String args[])
        {
            // Create a set of String
            Set<Integer> setOfInteger = new HashSet<>(
                Arrays.asList(2, 4, 6, 8, 10));

            // Print the set of Integer
            System.out.println("Set of Integer: " + setOfInteger);

            // Convert Set of Stream
            Stream<Integer>
                streamOfInteger = convertSetToStream(setOfInteger);

            // Print the Stream of Integer
            System.out.println("Stream of Integer: "
                               + Arrays.toString(
                                 streamOfInteger.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Set of Integer: [2, 4, 6, 8, 10]
    Stream of Integer: [2, 4, 6, 8, 10]

    ```

2.  **Using Predicate to filter the Stream**: In this method filter(Predicate) method is used that returns a stream consisting of elements that match the given predicate condition. The Functional Interface Predicate is defined in the java.util.Function package and can therefore be used as the assignment target for a lambda expression or method reference. It improves manageability of code, helps in unit-testing them separately

    **算法**:

    1.  获取要转换的集合。
    2.  通过使用预定义的静态方法或通过重写谓词接口创建新方法来定义谓词条件。在这个程序中，接口被覆盖以匹配以“G”开头的字符串。
    3.  将集合转换为流。这是使用 Set.stream()完成的。
    4.  使用定义的谓词条件过滤获得的流
    5.  已获得所需的流。返回/打印流。

    ```
    // Java Program to convert
    // Set to Stream in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.*;

    class GFG {

        // Generic function to convert a set to stream
        private static <T> Stream<T>
        convertSetToStream(Set<T> set, Predicate<T> predicate)
        {
            return set.stream()
                .filter(predicate);
        }

        // Main method
        public static void main(String args[])
        {
            // Create a set of String
            Set<String>
                setOfString = new HashSet<>(
                    Arrays.asList("GeeksForGeeks",
                                  "A computer portal",
                                  "for",
                                  "Geeks"));

            // Print the set of String
            System.out.println("Set of String: " + setOfString);

            // Create the predicate for item starting with G
            Predicate<String> predicate = new Predicate<String>() {
                @Override
                public boolean test(String s)
                {
                    // filter items that start with "G"
                    return s.startsWith("G");
                }
            };

            // Convert Set of Stream
            Stream<String>
                streamOfString = convertSetToStream(setOfString, predicate);

            // Print the filter Stream of String
            System.out.println("Stream from List with items"
                               + " starting with G: ");

            System.out.println(Arrays.toString(
                streamOfString.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Set of String: [for, Geeks, GeeksForGeeks, A computer portal]
    Stream from List with items starting with G: 
    [Geeks, GeeksForGeeks]

    ```