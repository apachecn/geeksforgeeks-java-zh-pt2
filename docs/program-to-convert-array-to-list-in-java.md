# 用 Java 将数组转换为列表的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-array-to-list-in-Java/](https://www.geeksforgeeks.org/program-to-convert-array-to-list-in-java/)

一个[数组](https://www.geeksforgeeks.org/arrays-in-java/)是一组相似类型的变量，它们被一个共同的名字所引用。根据数组的定义，数组可以包含基元数据类型以及类的对象。在原语数据类型的情况下，实际值存储在连续的内存位置。对于类的对象，实际的对象存储在堆段中。

[Java.util.List](https://www.geeksforgeeks.org/list-interface-java-examples/) 是 Collection 的子接口。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。列表接口由数组列表、链表、向量和堆栈类实现。

**示例:**

> **输入:**数组:【极客、伪造者、电脑入口】
> **输出:**列表:【极客、伪造者、电脑入口】
> 
> **输入:**数组:[1，2，3，4，5]
> **输出:**列表:[1，2，3，4，5]

下面是用 Java 将数组转换为列表的方法:

1.  **Brute Force or Naive Method**: In this method, an empty List is created and all elements present of the Array are added to it one by one.

    **算法**:

    1.  获取要转换的数组。
    2.  创建一个空列表
    3.  迭代数组中的项。
    4.  对于每个项目，将其添加到列表中
    5.  返回形成的列表

    **程序:**

    ```java
    // Java Program to convert
    // Array to List

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert an Array to List
        public static <T> List<T> convertArrayToList(T array[])
        {

            // Create an empty List
            List<T> list = new ArrayList<>();

            // Iterate through the array
            for (T t : array) {
                // Add each element into the list
                list.add(t);
            }

            // Return the converted List
            return list;
        }

        public static void main(String args[])
        {
            // Create an Array
            String array[] = { "Geeks", "forGeeks",
                                        "A Computer Portal" };

            // Print the Array
            System.out.println("Array: " 
                           + Arrays.toString(array));

            // convert the Array to List
            List<String>
                list = convertArrayToList(array);

            // Print the List
            System.out.println("List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Array: [Geeks, forGeeks, A computer Portal]
    List: [Geeks, forGeeks, A computer Portal]

    ```

2.  **Using Arrays.asList() method**: In this method, the Array is passed as the parameter into the List constructor with the help of Arrays.asList() method.

    **算法**:

    1.  获取要转换的数组。
    2.  在 Arrays.asList()方法的帮助下，通过将数组作为参数传递给列表的构造函数来创建列表
    3.  返回形成的列表

    **程序:**

    ```java
    // Java Program to convert
    // Array to List

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert an Array to List
        public static <T> List<T> convertArrayToList(T array[])
        {

            // Create the List by passing the Array
            // as parameter in the constructor
            List<T> list = Arrays.asList(array);

            // Return the converted List
            return list;
        }

        public static void main(String args[])
        {
            // Create an Array
            String array[] = { "Geeks", "forGeeks",
                                        "A computer Portal" };

            // Print the Array
            System.out.println("Array: " 
                               + Arrays.toString(array));

            // convert the Array to List
            List<String>
                list = convertArrayToList(array);

            // Print the List
            System.out.println("List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Array: [Geeks, forGeeks, A computer Portal]
    List: [Geeks, forGeeks, A computer Portal]

    ```