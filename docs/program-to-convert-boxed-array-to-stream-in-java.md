# 用 Java 将装箱数组转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-box-array-to-stream-in-Java/](https://www.geeksforgeeks.org/program-to-convert-boxed-array-to-stream-in-java/)

一个[数组](https://www.geeksforgeeks.org/arrays-in-java/)是一组相似类型的变量，它们被一个共同的名字所引用。根据数组的定义，数组可以包含基元数据类型以及类的对象。在原语数据类型的情况下，实际值存储在连续的内存位置。对于类的对象，实际的对象存储在堆段中。

装箱数组是以对象的形式定义的数组，而不是基元。
例:int a = 4；

**示例:**

> **输入:**数组:【极客、伪造者、电脑入口】
> **输出:**流:【极客、伪造者、电脑入口】
> 
> **输入:**数组:[1，2，3，4，5]
> **输出:**流:[1，2，3，4，5]

以下是用 Java 将装箱数组转换为流的方法:

1.  **Using Arrays.stream()**:

    **算法**:

    1.  获取要转换的数组。
    2.  通过将数组作为参数传递，使用 Arrays.stream()方法将数组转换为流。
    3.  返回形成的流

    **程序:**

    ```
    // Java Program to convert
    // Array to Stream

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert 
        // an Array to Stream
        public static <T> Stream<T> 
                    convertArrayToStream(T array[])
        {

            // Return the converted Stream
            return Arrays.stream(array);
        }

        public static void main(String args[])
        {
            // Create an Array
            String array[] = { "Geeks", "forGeeks", 
                                        "A Computer Portal" };

            // Print the Array
            System.out.println("Array: "
                                    + Arrays.toString(array));

            // convert the Array to Stream
            Stream<String>
                stream = convertArrayToStream(array);

            // Print the Stream
            System.out.println("Stream: " 
                        + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Array: [Geeks, forGeeks, A computer Portal]
    Stream: [Geeks, forGeeks, A computer Portal]

    ```

2.  **Using Stream.of()**: Stream.of() method creates a Stream directly with the values or collection passed as the parameter.

    **算法**:

    1.  获取要转换的数组。
    2.  通过将数组作为参数传递，使用 Stream.of()方法将数组转换为流。
    3.  返回形成的流

    **程序:**

    ```
    // Java Program to convert
    // Array to Stream

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert
        // an Array to Stream
        public static <T> Stream<T> 
                convertArrayToStream(T array[])
        {

            // Return the converted Stream
            return Stream.of(array);
        }

        public static void main(String args[])
        {
            // Create an Array
            String array[] = { "Geeks", "forGeeks", 
                                        "A Computer Portal" };

            // Print the Array
            System.out.println("Array: "
                                + Arrays.toString(array));

            // convert the Array to Stream
            Stream<String>
                stream = convertArrayToStream(array);

            // Print the Stream
            System.out.println("Stream: " 
                            + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Array: [Geeks, forGeeks, A computer Portal]
    Stream: [Geeks, forGeeks, A computer Portal]

    ```

3.  **Using List.stream()**: This is an indirect method in which the array is first converted into a List using Arrays.asList() method. Then the formed list is converted into a Stream using List.stream() method.

    **算法**:

    1.  获取要转换的数组。
    2.  通过将数组作为参数传递，使用 Arrays.asList()方法将数组转换为列表。
    3.  使用 List.stream()方法将形成的列表转换为流。
    4.  返回形成的流

    **程序:**

    ```
    // Java Program to convert
    // Array to Stream

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert 
        // an Array to Stream
        public static <T> Stream<T> 
                    convertArrayToStream(T array[])
        {

            // Return the converted Stream
            return Arrays
                .asList(array)
                .stream();
        }

        public static void main(String args[])
        {
            // Create an Array
            String array[] = { "Geeks", "forGeeks", 
                                        "A Computer Portal" };

            // Print the Array
            System.out.println("Array: " 
                            + Arrays.toString(array));

            // convert the Array to Stream
            Stream<String>
                stream = convertArrayToStream(array);

            // Print the Stream
            System.out.println("Stream: " 
                       + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Array: [Geeks, forGeeks, A computer Portal]
    Stream: [Geeks, forGeeks, A computer Portal]

    ```