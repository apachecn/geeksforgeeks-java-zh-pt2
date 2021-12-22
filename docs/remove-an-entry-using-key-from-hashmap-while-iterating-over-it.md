# 迭代一个条目时，使用键从哈希表中移除该条目

> 原文:[https://www . geeksforgeeks . org/从 hashmap 中移除条目，同时对其进行迭代/](https://www.geeksforgeeks.org/remove-an-entry-using-key-from-hashmap-while-iterating-over-it/)

给定一个 HashMap 和一个 Java 中的键，任务是使用键从这个 HashMap 中移除一个条目，同时迭代它。

**示例:**

```java
Input: HashMap: {1=Geeks, 2=ForGeeks, 3=GeeksForGeeks}, key = 2
Output: {1=Geeks, 3=GeeksForGeeks}

Input: HashMap: {1=G, 2=e, 3=e, 4=k, 5=s}, key = 3
Output: {1=G, 2=e, 4=k, 5=s}

```

*   **Using Java 7 and before:**
    1.  获取哈希表和密钥
    2.  使用 HashMap.iterate()方法创建一个迭代器来迭代 HashMap。
    3.  使用 Iterator.hasNext()方法迭代 HashMap。
    4.  迭代时，检查该迭代的键是否等于指定的键。地图的进入键可以通过 entry.getKey()方法获得。
    5.  如果关键字匹配，则使用 remove()方法从 HashMap 中移除该迭代的条目。
    6.  所需条目已成功删除。

    **程序:**

    ```java
    // Java program to remove an entry using key
    // from a HashMap while iterating over it

    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create a HashMap
            HashMap<Integer, String>
                map = new HashMap<>();

            // Populate the HashMap
            map.put(1, "Geeks");
            map.put(2, "ForGeeks");
            map.put(3, "GeeksForGeeks");

            // Get the key to be removed
            int keyToBeRemoved = 2;

            // Print the initial HashMap
            System.out.println("Original HashMap: "
                               + map);

            // Get the iterator over the HashMap
            Iterator<Map.Entry<Integer, String> >
                iterator = map.entrySet().iterator();

            // Iterate over the HashMap
            while (iterator.hasNext()) {

                // Get the entry at this iteration
                Map.Entry<Integer, String>
                    entry
                    = iterator.next();

                // Check if this key is the required key
                if (keyToBeRemoved == entry.getKey()) {

                    // Remove this entry from HashMap
                    iterator.remove();
                }
            }

            // Print the modified HashMap
            System.out.println("Modified HashMap: "
                               + map);
        }
    }
    ```

    **Output:**

    ```java
    Original HashMap: {1=Geeks, 2=ForGeeks, 3=GeeksForGeeks}
    Modified HashMap: {1=Geeks, 3=GeeksForGeeks}

    ```

*   **Using Java 8 lambda expressions:**
    1.  获取哈希表和密钥
    2.  使用 HashMap.entrySet()方法获取此地图的条目集。
    3.  使用 lambda 表达式，如果键等于指定的键，则从映射中移除该项。地图的进入键可以通过 entry.getKey()方法获得。
    4.  所需条目已成功删除。

    **程序:**

    ```java
    // Java program to remove an entry using key
    // from a HashMap while iterating over it

    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create a HashMap
            HashMap<Integer, String>
                map = new HashMap<>();

            // Populate the HashMap
            map.put(1, "Geeks");
            map.put(2, "ForGeeks");
            map.put(3, "GeeksForGeeks");

            // Get the key to be removed
            int keyToBeRemoved = 2;

            // Print the initial HashMap
            System.out.println("Original HashMap: "
                               + map);

            // Remove the specified entry from the Map
            map.entrySet()
                .removeIf(
                    entry -> (keyToBeRemoved == entry.getKey()));

            // Print the modified HashMap
            System.out.println("Modified HashMap: "
                               + map);
        }
    }
    ```

    **Output:**

    ```java
    Original HashMap: {1=Geeks, 2=ForGeeks, 3=GeeksForGeeks}
    Modified HashMap: {1=Geeks, 3=GeeksForGeeks}

    ```