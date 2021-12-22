# Java 中字符串列表转换为整数列表的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-list-to-list-of-integer-in-Java/](https://www.geeksforgeeks.org/program-to-convert-list-of-string-to-list-of-integer-in-java/)

列表是集合的一个子接口。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。列表接口由数组列表、链表、向量和堆栈类实现。

1.  **Using Java 8 Stream API**: A [Stream](https://www.geeksforgeeks.org/stream-in-java/) is a sequence of objects that supports various methods which can be pipelined to produce the desired result.

    Java 8 Stream API 可用于将**列表<integer>转换为<string>列表</string></integer>列表**。

    **算法**:

    1.  获取字符串列表。
    2.  将字符串列表转换为字符串流。这是使用 List.stream()完成的。
    3.  将字符串流转换为整数流。这是通过使用 Stream.map()并将 Integer.parseInt()方法作为 lambda 表达式传递来完成的。
    4.  将整数流收集到整数列表中。这是使用 Collectors.toList()完成的。
    5.  返回/打印字符串列表。

    **程序:**

    ```
    // Java Program to convert
    // List<String> to List<Integer> in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.*;

    class GFG {

        // Generic function to convert List of
        // String to List of Integer
        public static <T, U> List<U>
        convertStringListToIntList(List<T> listOfString,
                                   Function<T, U> function)
        {
            return listOfString.stream()
                .map(function)
                .collect(Collectors.toList());
        }

        public static void main(String args[])
        {

            // Create a list of String
            List<String> listOfString = Arrays.asList("1", "2", "3",
                                                           "4", "5");

            // Print the list of String
            System.out.println("List of String: " + listOfString);

            // Convert List of String to list of Integer
            List<Integer> listOfInteger = convertStringListToIntList(
                listOfString,
                Integer::parseInt);

            // Print the list of Integer
            System.out.println("List of Integer: " + listOfInteger);
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

    1.  获取字符串列表。
    2.  使用 Lists.transform()将字符串列表转换为整数列表。这是通过将 Integer.parseInt()方法作为 lambda 表达式进行转换来实现的。
    3.  返回/打印字符串列表。

    **程序:**

    ```
    // Java Program to convert
    // List<String> to List<Integer> in Java 8

    import com.google.common.base.Function;
    import com.google.common.collect.Lists;
    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert List of
        // String to List of Integer
        public static <T, U> List<U>
        convertStringListToIntList(List<T> listOfString,
                                   Function<T, U> function)
        {
            return Lists.transform(listOfString, function);
        }

        public static void main(String args[])
        {

            // Create a list of String
            List<String> listOfString = Arrays.asList("1", "2", "3",
                                                          "4", "5");

            // Print the list of String
            System.out.println("List of String: " + listOfString);

            // Convert List of String to list of Integer
            List<Integer>
                listOfInteger = convertStringListToIntList(listOfString,
                                                     Integer::parseInt);

            // Print the list of Integer
            System.out.println("List of Integer: " + listOfInteger);
        }
    }
    ```

    **Output:**

    ```
    List of String: [1, 2, 3, 4, 5]
    List of Integer: [1, 2, 3, 4, 5]

    ```