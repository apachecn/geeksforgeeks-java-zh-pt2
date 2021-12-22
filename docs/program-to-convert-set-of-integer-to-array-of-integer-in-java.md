# 在 Java 中将整数集转换为整数数组的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-set-of-of-of-integer-in-Java/](https://www.geeksforgeeks.org/program-to-convert-set-of-integer-to-array-of-integer-in-java/)

[Java Set](https://www.geeksforgeeks.org/set-in-java/) 是 java.util 包的一部分，扩展了 java.util.Collection 接口。它不允许使用重复元素，最多只能容纳一个空元素。

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。Java 8 Stream API 可用于将**设置<integer>转换为<string>设置</string></integer>T6。**

1.  **使用 Java 8 Stream** :一个 [Stream](https://www.geeksforgeeks.org/stream-in-java/) 是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。Java 8 Stream API 可以用来将 Set <integer>转换为 int[]。

    **算法** :

    1.  获取整数集。
    2.  将整数集转换为整数流。
        这是使用 Set.stream()完成的。
    3.  将整数流转换为整数流。
    4.  将 IntStream 转换为 int[]。
        这是使用 IntStream.toArray()完成的。
    5.  返回/打印整数数组 int[]

    **程序:**

    ```
    // Java Program to convert
    // Set<Integer> to int[] in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.Function;

    class GFG {

        // Function to convert Set of Integer to Set of String
        public static int[] convertIntSetToStringSet(
                                     Set<Integer> setOfInteger)
        {
            return setOfInteger.stream()
                .mapToInt(Integer::intValue)
                .toArray();
        }

        public static void main(String args[])
        {
            // Create a set of integers
            Set<Integer> setOfInteger = new HashSet<>(
                Arrays.asList(1, 2, 3, 4, 5));

            // Print the set of Integer
            System.out.println("Set of Integer: " + setOfInteger);

            // Convert Set of integers to set of String
            int[] intArray = convertIntSetToStringSet(setOfInteger);

            // Print the set of String
            System.out.println("Array of Integer: "
                               + Arrays.toString(intArray));
        }
    }
    ```

    **输出:**

    ```
    Set of Integer: [1, 2, 3, 4, 5]
    Array of Integer: [1, 2, 3, 4, 5]

    ```</integer> 
2.  **使用番石榴 ints to array()**:番石榴 ints to array()可用于将一组整数转换为一组整数。

    T43】算法 :

    1.  获取整数集
    2.  通过番石榴库的 Ints.toArray()方法创建一个整数数组，通过将整数集作为参数传递给这个方法。
    3.  返回/打印创建的整数数组 int[]

    **程序:**

    ```
    // Java Program to convert
    // Set<Integer> to int[] in Java 8

    import com.google.common.primitives.Ints;
    import java.util.*;
    import java.util.stream.*;
    import java.util.function.Function;

    class GFG {

        // Function to convert Set of Integer
        // to Set of String
        public static int[] convertIntSetToStringSet(
                                  Set<Integer> setOfInteger)
        {
            return Ints.toArray(setOfInteger);
        }

        public static void main(String args[])
        {
            // Create a set of integers
            Set<Integer> setOfInteger = new HashSet<>(
                Arrays.asList(1, 2, 3, 4, 5));

            // Print the set of Integer
            System.out.println("Set of Integer: " + setOfInteger);

            // Convert Set of integers to set of String
            int[] intArray = convertIntSetToStringSet(setOfInteger);

            // Print the set of String
            System.out.println("Array of Integer: "
                               + Arrays.toString(intArray));
        }
    }
    ```

    **输出:**

    ```
    Set of Integer: [1, 2, 3, 4, 5]
    Array of Integer: [1, 2, 3, 4, 5]

    ```

3.  **使用 Apache Commons to primitive()**:Apache Commons Lang 的 ArrayUtils 类提供了 toPrimitive()方法，可以将对象整数数组转换为基元整数。这组整数需要转换成整数数组。

    **算法** :

    1.  获取整数集合
    2.  通过 Apache Commons Lang 库的 ArrayUtils.toPrimitive()方法创建一个 primitive int 的对象
    3.  使用 to array()方法将这个 Primitive int 转换为整数数组。
    4.  返回/打印创建的整数数组 int[]

    **程序:**

    ```
    // Java Program to convert
    // Set<Integer> to int[] in Java 8

    import org.apache.commons.lang.ArrayUtils;
    import java.util.*;
    import java.util.stream.*;
    import java.util.function.Function;

    class GFG {

        // Function to convert Set of Integer
        // to Set of String
        public static int[] convertIntSetToStringSet(
                                Set<Integer> setOfInteger)
        {
            return ArrayUtils
                .toPrimitive(setOfInteger
                                 .toArray(new Integer[0]));
        }

        public static void main(String args[])
        {
            // Create a set of integers
            Set<Integer> setOfInteger = new HashSet<>(
                Arrays.asList(1, 2, 3, 4, 5));

            // Print the set of Integer
            System.out.println("Set of Integer: " + setOfInteger);

            // Convert Set of integers to set of String
            int[] intArray = convertIntSetToStringSet(setOfInteger);

            // Print the set of String
            System.out.println("Array of Integer: "
                               + Arrays.toString(intArray));
        }
    }
    ```

    **输出:**

    ```
    Set of Integer: [1, 2, 3, 4, 5]
    Array of Integer: [1, 2, 3, 4, 5]

    ```