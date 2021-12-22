# 用 Java 将集合转换为列表的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-set-to-list-in-Java/](https://www.geeksforgeeks.org/program-to-convert-set-to-list-in-java/)

[Java Set](https://www.geeksforgeeks.org/set-in-java/) 是 java.util 包的一部分，扩展了 java.util.Collection 接口。它不允许使用重复元素，最多只能容纳一个空元素。

[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)是收藏的子界面。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。列表接口由数组列表、链表、向量和堆栈类实现。

下面是用 Java 将集合转换为列表的方法。

1.  **Brute Force or Naive method**: This method includes creating an empty list and add every element of the set to it.

    **算法**:

    1.  获取要转换的集合。
    2.  创建一个空列表
    3.  将集合中的每个元素推入列表
    4.  返回形成的**列表**

    **程序:**

    ```java
    // Java Program to convert
    // Set to List in Java 8

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert set to list
        public static <T> List<T> convertSetToList(Set<T> set)
        {
            // create an empty list
            List<T> list = new ArrayList<>();

            // push each element in the set into the list
            for (T t : set)
                list.add(t);

            // return the list
            return list;
        }

        public static void main(String args[])
        {

            // Create a Set using HashSet
            Set<String> hash_Set = new HashSet<String>();

            // Add elements to set
            hash_Set.add("Geeks");
            hash_Set.add("For");
            hash_Set.add("Geeks");
            hash_Set.add("Example");
            hash_Set.add("Set");

            // Print the Set
            System.out.println("Set: " + hash_Set);

            // construct a new List from Set
            List<String> list = convertSetToList(hash_Set);

            // Print the List
            System.out.println("List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Set: [Set, Example, Geeks, For]
    List: [Set, Example, Geeks, For]

    ```

2.  **With help of Constructor**: Collections in Java have a constructor in which the direct set can be passed to create a List from it.

    **算法**:

    1.  获取要转换的集合。
    2.  通过将 set as 参数传递给构造函数来创建列表。
    3.  返回形成的**列表**

    **程序:**

    ```java
    // Java Program to convert
    // Set to List in Java 8

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert set to list
        public static <T> List<T> convertSetToList(Set<T> set)
        {
            // create a list from Set
            List<T> list = new ArrayList<>(set);

            // return the list
            return list;
        }

        public static void main(String args[])
        {

            // Create a Set using HashSet
            Set<String> hash_Set = new HashSet<String>();

            // Add elements to set
            hash_Set.add("Geeks");
            hash_Set.add("For");
            hash_Set.add("Geeks");
            hash_Set.add("Example");
            hash_Set.add("Set");

            // Print the Set
            System.out.println("Set: " + hash_Set);

            // construct a new List from Set
            List<String> list = convertSetToList(hash_Set);

            // Print the List
            System.out.println("List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Set: [Set, Example, Geeks, For]
    List: [Set, Example, Geeks, For]

    ```

3.  **Using Java 8 Stream**: In Java 8, Stream can be used convert a set to a list by converting the set to a sequential Stream using Set.stream() and using a Collector to collect the input elements into a new List.

    **算法**:

    1.  获取要转换的 HashMap。
    2.  从集合中创建流
    3.  将集合转换为列表并收集
    4.  返回收集的**列表**

    **程序:**

    ```java
    // Java Program to convert
    // HashMap to TreeMap in Java 8

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert set to list
        public static <T> List<T> convertSetToList(Set<T> set)
        {
            // create a list from Set
            return set

                // Create stream from the Set
                .stream()

                // Convert the set to list and collect it
                .collect(Collectors.toList());
        }

        public static void main(String args[])
        {

            // Create a Set using HashSet
            Set<String> hash_Set = new HashSet<String>();

            // Add elements to set
            hash_Set.add("Geeks");
            hash_Set.add("For");
            hash_Set.add("Geeks");
            hash_Set.add("Example");
            hash_Set.add("Set");

            // Print the Set
            System.out.println("Set: " + hash_Set);

            // construct a new List from Set
            List<String> list = convertSetToList(hash_Set);

            // Print the List
            System.out.println("List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Set: [Set, Example, Geeks, For]
    List: [Set, Example, Geeks, For]

    ```

4.  **Using Guava Library List.newArrayList(set)**: Lists.newArrayList(set) creates a mutable ArrayList instance containing the elements of the specified set.

    **算法**:

    1.  获取要转换的集合。
    2.  使用 Lists.newArrayList()创建一个新列表，方法是将 set 作为参数传递给 Guava 库的这个函数
    3.  返回形成的**列表**

    **程序:**

    ```java
    // Java Program to convert
    // HashMap to TreeMap in Java 8

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Generic function to convert set to list
        public static <T> List<T> convertSetToList(Set<T> set)
        {
            // create a list from Set
            return Lists.newArrayList(set);
        }

        public static void main(String args[])
        {

            // Create a Set using HashSet
            Set<String> hash_Set = new HashSet<String>();

            // Add elements to set
            hash_Set.add("Geeks");
            hash_Set.add("For");
            hash_Set.add("Geeks");
            hash_Set.add("Example");
            hash_Set.add("Set");

            // Print the Set
            System.out.println("Set: " + hash_Set);

            // construct a new List from Set
            List<String> list = convertSetToList(hash_Set);

            // Print the List
            System.out.println("List: " + list);
        }
    }
    ```

    **输出:**

    ```java
    Set: [Set, Example, Geeks, For]
    List: [Set, Example, Geeks, For]

    ```