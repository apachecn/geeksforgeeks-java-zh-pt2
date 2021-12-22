# util。数组与反射。Java 中的数组示例

> 原文:[https://www . geesforgeks . org/util-arrays-vs-reflect-array-in-Java-with-examples/](https://www.geeksforgeeks.org/util-arrays-vs-reflect-array-in-java-with-examples/)

**先决条件:** [阵类](https://www.geeksforgeeks.org/reflection-array-class-in-java/)[阵类](https://www.geeksforgeeks.org/array-class-in-java/)

java.lang.reflect 包中的[数组类是 Java Reflection 的一部分。这个类提供了动态创建和访问 Java 数组的静态方法。它是一个最终类，这意味着它不能被实例化或更改。类名本身只能使用这个类的方法。](https://www.geeksforgeeks.org/reflection-array-class-in-java/)

java.util 包中的[数组类是 java 集合框架的一部分。这个类提供了动态创建和访问 Java 数组的静态方法。它只包含静态方法和对象类的方法。这个类的方法可以由类名本身使用。](https://www.geeksforgeeks.org/array-class-in-java/)

**数组和 Java 中数组的区别:**

1.  **The package of existence:**
    The Array class exists in the **java.lang.reflect package** whereas the Arrays class exists in the **java.util package**.

    **数组的类层次:**

    ```java
    java.lang.Object
     ↳ java.lang.reflect
      ↳ Class Array

    ```

    **数组的类层次结构:**

    ```java
    java.lang.Object
     ↳ java.util
      ↳ Class Arrays

    ```

2.  **Immutability:**
    The Array class is immutable in nature whereas the Arrays class is not. By immutable, it means that the class cannot be extended or inherited. The Array class is declared as final to achieve immutability.

    **数组的类声明:**

    ```java
    public final class Array
        extends Object

    ```

    **数组的类声明:**

    ```java
    public class Arrays
        extends Object

    ```

3.  **Usage:**
    The **[java.util.Arrays class](https://www.geeksforgeeks.org/array-class-in-java/)** contains various methods for manipulating arrays (such as sorting and searching) whereas this **java.lang.reflect.Array class** provides static methods to dynamically create and access Java arrays. This Array class keeps the array to be type-safe.

    **示例:**

    ```java
    // Java program to show Array vs Arrays

    import java.lang.reflect.Array;
    import java.util.Arrays;

    public class GfG {
        public static void main(String[] args)
        {

            // Get the size of the array
            int[] intArray = new int[5];

            // Add elements into the array
            // using reflect.Array class
            Array.setInt(intArray, 0, 10);

            // Printing the Array content
            // using util.Arrays class
            System.out.println(
                Arrays.toString(intArray));
        }
    }
    ```

    **Output:**

    ```java
    [10, 0, 0, 0, 0]

    ```