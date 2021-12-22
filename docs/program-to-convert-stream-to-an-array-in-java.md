# 用 Java 将流转换成数组的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-stream-to-a-array-in-Java/](https://www.geeksforgeeks.org/program-to-convert-stream-to-an-array-in-java/)

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。

一个[数组](https://www.geeksforgeeks.org/arrays-in-java/)是一组相似类型的变量，它们被一个共同的名字所引用。根据数组的定义，数组可以包含基元数据类型以及类的对象。在原语数据类型的情况下，实际值存储在连续的内存位置。对于类的对象，实际的对象存储在堆段中。

以下是将流转换为数组的各种方法:

1.  **Using toArray()**: Stream provides toArray() method that returns an array containing the elements of the stream in the form of Object array.

    **语法:**

    ```java
    stream.toArray()
    ```

    **算法**:

    1.  获取流
    2.  使用 Stream.toArray()方法将流转换为数组。
    3.  获得的数组属于对象[]类型
    4.  返回数组对象[]

    **程序:**

    ```java
    // Java Program to convert
    // Stream to array in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.Function;

    class GFG {

        // Function to convert Stream to Array
        public static <T> Object[] convertStreamToArray(Stream<T> stream)
        {
            return stream.toArray();
        }

        public static void main(String args[])
        {
            // Create a stream of integers
            Stream<Integer> stream = Stream.of(1, 2, 3, 4, 5);

            // Convert Stream to array
            Object[] array = convertStreamToArray(stream);

            // Print the array of stream
            System.out.println("Array from Stream: "
                               + Arrays.toString(array));
        }
    }
    ```

    **Output:**

    ```java
    Array from Stream: [1, 2, 3, 4, 5]

    ```

2.  **Using toArray(IntFunction** : This method returns an array containing the elements of this stream, using the provided generator function to allocate the returned array, as well as any additional arrays that might be required for a partitioned execution or for resizing.

    **语法:**

    ```java
    <A> A[] toArray(IntFunction<A[]> generator)
    ```

    **算法**:

    1.  获取流
    2.  使用 Stream.toArray()方法将 Stream 转换为数组，方法是将 Object[]:new 作为生成器函数来分配返回的数组。
    3.  获得的数组属于对象[]类型
    4.  返回数组对象[]

    **程序:**

    ```java
    // Java Program to convert
    // Stream to array in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.Function;

    class GFG {

        // Function to convert Stream to Array
        public static <T> Object[] convertStreamToArray(Stream<T> stream)
        {
            return stream.toArray(Object[] ::new);
        }

        public static void main(String args[])
        {

            // Create a stream of integers
            Stream<Integer> stream = Stream.of(1, 2, 3, 4, 5);

            // Convert Stream to array
            Object[] array = convertStreamToArray(stream);

            // Print the array of stream
            System.out.println("Array from Stream: "
                               + Arrays.toString(array));
        }
    }
    ```

    **Output:**

    ```java
    Array from Stream: [1, 2, 3, 4, 5]

    ```

3.  **Stream <integer>to int[] using mapToInt()</integer>**: Java 8 Stream API provides mapToInt() method that returns an IntStream consisting of the results of applying the given function to the elements of this stream. This is an intermediate operation. The obtained IntStream is then converted into int[] using toArray().

    **算法**:

    1.  获取整数流
    2.  使用 Stream.mapToInt()方法将流转换为输入流。
    3.  使用 toArray()将获得的 IntStream 转换为 int[]
    4.  获得的数组是整数类型的
    5.  返回数组 int[]

    **程序:**

    ```java
    // Java Program to convert
    // Stream to array in Java 8

    import java.util.*;
    import java.util.stream.*;
    import java.util.function.Function;

    class GFG {

        // Function to convert Stream to Array
        public static int[] convertStreamToArray(Stream<Integer> stream)
        {
            return stream.mapToInt(Integer::intValue).toArray();
        }

        public static void main(String args[])
        {

            // Create a stream of integers
            Stream<Integer> stream = Stream.of(1, 2, 3, 4, 5);

            // Convert Stream to array
            int[] array = convertStreamToArray(stream);

            // Print the array of stream
            System.out.println("Array of Integer from Stream: "
                               + Arrays.toString(array));
        }
    }
    ```

    **Output:**

    ```java
    Array of Integer from Stream: [1, 2, 3, 4, 5]

    ```