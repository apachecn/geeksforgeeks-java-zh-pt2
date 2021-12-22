# 迭代一个条目时，使用哈希表中的值移除该条目

> 原文:[https://www . geesforgeks . org/remove-a-entry-use-value-from-hashmap-while-iterating-it/](https://www.geeksforgeeks.org/remove-an-entry-using-value-from-hashmap-while-iterating-over-it/)

给定一个 HashMap 和一个 Java 中的值，任务是使用该值从这个 HashMap 中移除一个条目，同时迭代它。

**示例:**

> **输入**:HashMap:{ 1 =极客，2 =极客，3 =极客暴客}，value =“极客”
> **输出**:{ 1 =极客，3 =极客暴客}
> 
> **输入** : HashMap: {1=G，2=e，3=e，4=k，5=s}，value = k
> **输出** : {1=G，2=e，3=e，5=s}

*   **Using Java 7 and before:**
    1.  获取哈希表和值
    2.  使用 HashMap.iterate()方法创建一个迭代器来迭代 HashMap。
    3.  使用 Iterator.hasNext()方法迭代 HashMap。
    4.  迭代时，检查该迭代的值是否等于指定的值。地图的入口值可以通过 entry.getValue()方法获得。
    5.  如果值匹配，则使用 remove()方法从 HashMap 中移除该迭代的条目。
    6.  所需条目已成功删除。

    **语法:**

    ```java
    Iterator> 
        iterator = map.entrySet().iterator();

    while (iterator.hasNext()) {
        Map.Entry <integer string="">entry = iterator.next();
        if (valueToBeRemoved.equals(entry.getValue())) {
            iterator.remove();
        }
    }</integer> 
    ```

    下面是上述方法的实现:

    ```java
    // Java program to remove an entry using value
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

            // Get the value to be removed
            String valueToBeRemoved = "ForGeeks";

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

                // Check if this value is the required value
                if (valueToBeRemoved.equals(entry.getValue())) {

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
    1.  获取哈希表和值
    2.  使用 HashMap.entrySet()方法获取此地图的条目集。
    3.  如果值等于指定的值，则使用 lambda 表达式从映射中移除条目。地图的入口值可以通过 entry.getValue()方法获得。
    4.  所需条目已成功删除。

    **语法:**

    ```java
    map.entrySet()
       .removeIf(
           entry -> (valueToBeRemoved
                        .equals(entry.getValue())));

    ```

    下面是上述方法的实现:

    ```java
    // Java program to remove an entry using value
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

            // Get the value to be removed
            String valueToBeRemoved = "ForGeeks";

            // Print the initial HashMap
            System.out.println("Original HashMap: "
                               + map);

            // Remove the specified entry from the Map
            map.entrySet()
                .removeIf(
                    entry -> (valueToBeRemoved.equals(entry.getValue())));

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