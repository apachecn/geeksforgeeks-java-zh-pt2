# 遍历 Java 中的 HashMap

> 原文:[https://www . geesforgeks . org/traverse-through-a-hashmap-in-Java/](https://www.geeksforgeeks.org/traverse-through-a-hashmap-in-java/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 是 java collections 框架的一部分。它内部使用[哈希](https://www.geeksforgeeks.org/hashing-set-1-introduction/)技术。

这篇文章包含了遍历 HashMap 的不同方法，如下所示:

1.  **Using an [Iterator](https://www.geeksforgeeks.org/iterators-in-java/):** Iterator is an interface in java.util package which is used to iterate through a collection.
    *   **hm.entrySet()** 用于检索所有名为 Map 的键值对。在内部输入并存储到一个集合中。
    *   **hm.entrySet()。iterator()** 返回一个迭代器，该迭代器充当光标，指向集合的第一个元素，并一直移动到最后。
    *   **hmIterator.hasNext()** 检查集合中的下一个元素，并返回一个布尔值
    *   **hmIterator.next()** 返回下一个元素(Map。条目)从集合中删除。
    *   **mapElement.getKey()** 返回关联地图的键。进入
    *   **mapElement.getValue()** 返回关联地图的值。进入

    **示例:**

    ```java
    // Java program to traverse through
    // a hashmap using iterator

    import java.util.*;

    class GfG {
        public static void main(String[] args)
        {
            // Consider the hashmap contains
            // student name and their marks
            HashMap<String, Integer> hm = 
                        new HashMap<String, Integer>();

            // Adding mappings to HashMap
            hm.put("GeeksforGeeks", 54);
            hm.put("A computer portal", 80);
            hm.put("For geeks", 82);

            // Printing the HashMap
            System.out.println("Created hashmap is" + hm);

            // Getting an iterator
            Iterator hmIterator = hm.entrySet().iterator();

            // Iterate through the hashmap
            // and add some bonus marks for every student
            System.out.println("HashMap after adding bonus marks:");

            while (hmIterator.hasNext()) {
                Map.Entry mapElement = (Map.Entry)hmIterator.next();
                int marks = ((int)mapElement.getValue() + 10);
                System.out.println(mapElement.getKey() + " : " + marks);
            }
        }
    }
    ```

    **Output:**

    ```java
    Created hashmap is{GeeksforGeeks=54, A computer portal=80, For geeks=82}
    HashMap after adding bonus marks:
    GeeksforGeeks : 64
    A computer portal : 90
    For geeks : 92

    ```

2.  **使用[进行每个循环](https://www.geeksforgeeks.org/for-each-loop-in-java/) :**

    ```java
    // Java program for traversing
    // through a hashmap using for-each loop

    import java.util.*;

    class GfG {
        public static void main(String[] args)
        {

            // Consider the hashmap containing
            // student name and their marks
            HashMap<String, Integer> hm = 
                         new HashMap<String, Integer>();

            // Adding mappings to HashMap
            hm.put("GeeksforGeeks", 54);
            hm.put("A computer portal", 80);
            hm.put("For geeks", 82);

            // Printing the HashMap
            System.out.println("Created hashmap is" + hm);

            // Loop through the hashmap
            System.out.println("HashMap after adding bonus marks:");

            // Using for-each loop
            for (Map.Entry mapElement : hm.entrySet()) {
                String key = (String)mapElement.getKey();

                // Add some bonus marks
                // to all the students and print it
                int value = ((int)mapElement.getValue() + 10);

                System.out.println(key + " : " + value);
            }
        }
    }
    ```

    **输出:**

    ```java
    Created hashmap is{GeeksforGeeks=54, A computer portal=80, For geeks=82}
    HashMap after adding bonus marks:
    GeeksforGeeks : 64
    A computer portal : 90
    For geeks : 92

    ```

3.  **使用 [forEach()](https://www.geeksforgeeks.org/stream-foreach-method-java-examples/) 方法:** forEach()是在 java 8 中引入的 hashmap 方法。它用于遍历 hashmap，也减少了代码行数。

    ```java
    // Java program for traversing
    // through a hashmap using for-each loop

    import java.util.*;

    class GfG {
        public static void main(String[] args)
        {

            // Consider the hashmap containing
            // student name and their marks
            HashMap<String, Integer> hm = 
                          new HashMap<String, Integer>();

            // Adding mappings to HashMap
            hm.put("GeeksforGeeks", 54);
            hm.put("A computer portal", 80);
            hm.put("For geeks", 82);

            // Printing the HashMap
            System.out.println("Created hashmap is" + hm);

            // Loop through the hashmap
            // and add bonus marks
            System.out.println("HashMap after adding bonus marks:");

            // Using Hashmap.forEach()
            hm.forEach((k, v) -> System.out.println(k + " : " + (v + 10)));
        }
    }
    ```

    **输出:**

    ```java
    Created hashmap is{GeeksforGeeks=54, A computer portal=80, For geeks=82}
    HashMap after adding bonus marks:
    GeeksforGeeks : 64
    A computer portal : 90
    For geeks : 92

    ```