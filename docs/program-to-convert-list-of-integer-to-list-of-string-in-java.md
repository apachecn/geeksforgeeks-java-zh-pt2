# 用 Java 将整数列表转换成字符串列表的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-list-of-to-list-of-string-in-Java/](https://www.geeksforgeeks.org/program-to-convert-list-of-integer-to-list-of-string-in-java/)

列表是集合的一个子接口。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。列表接口由数组列表、链表、向量和堆栈类实现。

1.  **Using Java 8 Stream API**: A [Stream](https://www.geeksforgeeks.org/stream-in-java/) is a sequence of objects that supports various methods which can be pipelined to produce the desired result.

    Java 8 Stream API 可用于将**列表<string>转换为<integer>列表</integer></string>列表**。

    **算法**:

    1.  获取整数列表。
    2.  将整数列表转换为整数流。这是使用 List.stream()完成的。
    3.  将整数流转换为字符串流。这是通过使用 Stream.map()并将 s -> String.valueOf 方法作为 lambda 表达式传递来实现的。
    4.  将字符串流收集到字符串列表中。这是使用 Collectors.toList()完成的。
    5.  返回/打印字符串列表。

    **程序:**

    ```
    // Java Program to convert
    // List<Integer> to List<String> in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.*;

    class GFG {

        // Generic function to convert List of
        // String to List of String
        public static <T, U> List<U>
        convertIntListToStringList(List<T> listOfInteger,
                                   Function<T, U> function)
        {
            return listOfInteger.stream()
                .map(function)
                .collect(Collectors.toList());
        }

        public static void main(String args[])
        {

            // Create a List of Integer
            List<Integer> listOfInteger = Arrays.asList(1, 2, 3, 4, 5);

            // Print the List of Integer
            System.out.println("List of Integer: " + listOfInteger);

            // Convert List of Integer to List of String
            List<String> listOfString = convertIntListToStringList(
                listOfInteger,
                s -> String.valueOf(s));

            // Print the List of String
            System.out.println("List of String: " + listOfString);
        }
    }
    ```

    **Output:**

    ```
    List of String: [1, 2, 3, 4, 5]
    List of Integer: [1, 2, 3, 4, 5]

    ```

2.  **Using Guava’s List.transform()**:

    **算法**:

    1.  获取整数列表。
    2.  使用 Lists.transform()将整数列表转换为字符串列表。这是通过将 s -> String.valueOf 方法作为 lambda 表达式进行转换来实现的。
    3.  返回/打印字符串列表。

    **程序:**

    ```
    // Java Program to convert
    // List<Integer> to List<String> in Java 8

    import com.google.common.base.Function;
    import com.google.common.collect.Lists;
    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert List of
        // String to List of String
        public static <T, U> List<U>
        convertIntListToStringList(List<T> listOfInteger,
                                   Function<T, U> function)
        {
            return Lists.transform(listOfInteger, function);
        }

        public static void main(String args[])
        {

            // Create a List of Integer
            List<Integer> listOfInteger = Arrays.asList(1, 2, 3, 4, 5);

            // Print the List of Integer
            System.out.println("List of Integer: " + listOfInteger);

            // Convert List of Integer to List of String
            List<String> listOfString = convertIntListToStringList(
                listOfInteger,
                s -> String.valueOf(s));

            // Print the List of String
            System.out.println("List of String: " + listOfString);
        }
    }
    ```

    **Output:**

    ```
    List of String: [1, 2, 3, 4, 5]
    List of Integer: [1, 2, 3, 4, 5]

    ```