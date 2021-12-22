# 用 Java 将基元数组转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-原语-array-to-stream-in-java/](https://www.geeksforgeeks.org/program-to-convert-primitive-array-to-stream-in-java/)

一个[数组](https://www.geeksforgeeks.org/arrays-in-java/)是一组相似类型的变量，它们被一个共同的名字所引用。根据数组的定义，数组可以包含基元数据类型以及类的对象。在原语数据类型的情况下，实际值存储在连续的内存位置。对于类的对象，实际的对象存储在堆段中。

基元数组是在基元包装类而不是对象的帮助下定义的数组。
例:整数 a =新整数(4)；

当一个基元数组被转换成流时，将会得到像 **IntStream、DoubleStream 和 LongStream** 这样的基元流。

**示例:**

> **输入:**双数组:【1.2，2.4，3.6，4.8，5.0】
> **输出:**双流:【1.2，2.4，3.6，4.8，5.0】
> 
> **输入:**整数数组:[1，2，3，4，5]
> **输出:**输入流:[1，2，3，4，5]

以下是在 Java 中将基元数组转换为流的方法:

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
        public static IntStream 
                    convertArrayToStream(int array[])
        {

            // Return the converted Stream
            return Arrays.stream(array);
        }

        public static void main(String args[])
        {
            // Create an Array
            int[] array = new int[] { 3, 2, 5, 4, 1 };

            // Print the Array
            System.out.println("Array: " 
                        + Arrays.toString(array));

            // convert the Array to Stream
            IntStream stream = convertArrayToStream(array);

            // Print the Stream
            System.out.println("Stream: " 
                        + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Array: [3, 2, 5, 4, 1]
    Stream: [3, 2, 5, 4, 1]

    ```

2.  **Using IntStream.of()**: The IntStream.of() method creates a Stream directly with the primitive values or collection passed as the parameter.

    **算法**:

    1.  获取要转换的数组。
    2.  通过将数组作为参数传递，使用 IntStream.of()方法将数组转换为流。
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
        public static IntStream 
                   convertArrayToStream(int array[])
        {

            // Return the converted Stream
            return IntStream.of(array);
        }

        public static void main(String args[])
        {
            // Create an Array
            int[] array = new int[] { 3, 2, 5, 4, 1 };

            // Print the Array
            System.out.println("Array: " 
                          + Arrays.toString(array));

            // convert the Array to Stream
            IntStream stream = convertArrayToStream(array);

            // Print the Stream
            System.out.println("Stream: " 
                          + Arrays.toString(stream.toArray()));
        }
    }
    ```

    **Output:**

    ```
    Array: [3, 2, 5, 4, 1]
    Stream: [3, 2, 5, 4, 1]

    ```