# 用 Java 将数组转换为集合的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-array-to-set-in-Java/](https://www.geeksforgeeks.org/program-to-convert-array-to-set-in-java/)

一个[数组](https://www.geeksforgeeks.org/arrays-in-java/)是一组相似类型的变量，它们被一个共同的名字所引用。根据数组的定义，数组可以包含基元数据类型以及类的对象。在原语数据类型的情况下，实际值存储在连续的内存位置。对于类的对象，实际的对象存储在堆段中。

[Java 中设置](https://www.geeksforgeeks.org/set-in-java/)是 java.util 包的一部分，扩展了 java.util.Collection 接口。它不允许使用重复元素，最多只能容纳一个空元素。Java Set 接口的几个重要特性如下:

*   set 接口是对象的无序集合，其中不能存储重复的值。
*   Java 集合不提供对元素插入或删除位置的控制。
*   基本上，Set 是由 HashSet、LinkedHashSet 或 TreeSet(排序表示)实现的。
*   Set 有各种添加、清除、大小等方法来增强这个界面的使用。

**示例:**

> **输入:**数组:【极客、伪造者、电脑入口】
> **输出:**集合:【极客、伪造者、电脑入口】
> 
> **输入:**数组:[1，2，3，4，5]
> **输出:**集合:[1，2，3，4，5]

以下是在 Java 中将数组转换为集合的方法:

1.  **Brute Force or Naive Method**: In this method, an empty Set is created and all elements present of the Array are added to it one by one.

    **算法**:

    1.  获取要转换的数组。
    2.  创建一个空集合
    3.  迭代数组中的项。
    4.  对于每个项目，将其添加到集合中
    5.  返回形成的集合

    **程序:**

    ```java
    // Java Program to convert
    // Array to Set

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert an Array to Set
        public static <T> Set<T> convertArrayToSet(T array[])
        {

            // Create an empty Set
            Set<T> set = new HashSet<>();

            // Iterate through the array
            for (T t : array) {
                // Add each element into the set
                set.add(t);
            }

            // Return the converted Set
            return set;
        }

        public static void main(String args[])
        {
            // Create an Array
            String array[] = { "Geeks", "forGeeks", 
                                         "A Computer Portal" };

            // Print the Array
            System.out.println("Array: " + Arrays.toString(array));

            // convert the Array to Set
            Set<String>
                set = convertArrayToSet(array);

            // Print the Set
            System.out.println("Set: " + set);
        }
    }
    ```

    **Output:**

    ```java
    Array: [Geeks, forGeeks, A computer Portal]
    Set: [Geeks, forGeeks, A computer Portal]

    ```

2.  **Using Arrays.asList() method**: In this method, the Array is passed as the parameter into the Set constructor in the form of an Array with the help of Arrays.asList() method.

    **算法**:

    1.  获取要转换的数组。
    2.  在 Arrays.asList()方法的帮助下，通过将数组作为参数传递给集合的构造函数来创建集合
    3.  返回形成的集合

    **程序:**

    ```java
    // Java Program to convert
    // Array to Set

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert an Array to Set
        public static <T> Set<T> convertArrayToSet(T array[])
        {

            // Create the Set by passing the Array
            // as parameter in the constructor
            Set<T> set = new HashSet<>(Arrays.asList(array));

            // Return the converted Set
            return set;
        }

        public static void main(String args[])
        {
            // Create an Array
            String array[] = { "Geeks", "forGeeks",
                                        "A computer Portal" };

            // Print the Array
            System.out.println("Array: " + Arrays.toString(array));

            // convert the Array to Set
            Set<String>
                set = convertArrayToSet(array);

            // Print the Set
            System.out.println("Set: " + set);
        }
    }
    ```

    **Output:**

    ```java
    Array: [Geeks, forGeeks, A computer Portal]
    Set: [Geeks, forGeeks, A computer Portal]

    ```