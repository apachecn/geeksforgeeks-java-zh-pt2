# 用 Java 将 HashMap 转换为 TreeMap 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-hashmap-to-tree map-in-Java/](https://www.geeksforgeeks.org/program-to-convert-hashmap-to-treemap-in-java/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 是 Java 1.2 以来 Java 集合的一部分。它提供了以(键、值)对存储数据的 Java Map 接口的基本实现。要访问 HashMap 中的值，必须知道它的键。哈希映射被称为哈希映射，因为它使用哈希技术来存储数据。

Java 中的[树图](https://www.geeksforgeeks.org/treemap-in-java/)和抽象类一起用来实现地图接口和导航地图。地图根据其关键字的自然顺序进行排序，或者由地图创建时提供的比较器进行排序，具体取决于使用的构造函数。这被证明是排序和存储键值对的有效方式。

下面是在 Java 中将 HashMap 转换成 TreeMap 的方法，这样得到的 TreeMap 应该包含 HashMap 的所有映射，按照它们的键的自然顺序排序。

**示例:**

> **输入:**HashMap:{ 1 =极客，2 =伪造者，3 =计算机门户}
> T3】输出:树形图:{ 1 =极客，2 =伪造者，3 =计算机门户}
> 
> **输入:**哈希表:{1=1，2=2，3=3}
> **输出:**树形图:{1=1，2=2，3=3}

以下是在 Java 中将 HashMap 转换为 TreeMap 的方法:

**1。在 Java 8 中**:这个方法包括将 HashMap 转换为 Stream，并使用 Stream.collect()方法收集 TreeMap 中的流元素，该方法接受一个收集器。

**算法**:

1.  获取要转换的 HashMap。
2.  从哈希表中获取条目
3.  将地图条目转换为流
4.  使用收集器，收集条目并将其转换为树形图
5.  现在收集树形图
6.  返回形成的**树形图**

**程序:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert
// HashMap to TreeMap in Java 8

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to construct a new 
    // TreeMap from HashMap
    public static <K, V> Map<K, V> convertToTreeMap(Map<K, V> hashMap)
    {
        Map<K, V>
            treeMap = hashMap
                          // Get the entries from the hashMap
                          .entrySet()

                          // Convert the map into stream
                          .stream()

                          // Now collect the returned TreeMap
                          .collect(
                              Collectors

                                  // Using Collectors, collect the entries
                                  // and convert it into TreeMap
                                  .toMap(
                                      Map.Entry::getKey,
                                      Map.Entry::getValue,
                                      (oldValue,
                                       newValue)
                                          -> newValue,
                                      TreeMap::new));

        // Return the TreeMap
        return treeMap;
    }

    public static void main(String args[])
    {
        // Create a HashMap
        Map<String, String> hashMap = new HashMap<>();

        // Add entries to the HashMap
        hashMap.put("1", "Geeks");
        hashMap.put("2", "forGeeks");
        hashMap.put("3", "A computer Portal");

        // Print the HashMap
        System.out.println("HashMap: " + hashMap);

        // construct a new TreeMap from HashMap
        Map<String, String> treeMap = convertToTreeMap(hashMap);

        // Print the TreeMap
        System.out.println("TreeMap: " + treeMap);
    }
}
```

**输出:**

```java
HashMap: {1=Geeks, 2=forGeeks, 3=A computer Portal}
TreeMap: {1=Geeks, 2=forGeeks, 3=A computer Portal}
```

**2。使用纯 Java** :在这个方法中，要么将 HashMap 实例传递给 TreeMap 构造函数，要么传递给 putAll()方法。这将直接从哈希表创建树形图。

**算法**:

1.  获取要转换的 HashMap。
2.  创建新的树形图
3.  将 hashMap 传递给 treeMap 的 putAll()方法
4.  返回形成的**树形图**

**程序:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert
// HashMap to TreeMap in Java 8

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to construct a 
    // new TreeMap from HashMap
    public static <K, V> Map<K, V> convertToTreeMap(Map<K, V> hashMap)
    {
        // Create a new TreeMap
        Map<K, V> treeMap = new TreeMap<>();

        // Pass the hashMap to putAll() method
        treeMap.putAll(hashMap);

        // Return the TreeMap
        return treeMap;
    }

    public static void main(String args[])
    {
        // Create a HashMap
        Map<String, String> hashMap = new HashMap<>();

        // Add entries to the HashMap
        hashMap.put("1", "Geeks");
        hashMap.put("2", "forGeeks");
        hashMap.put("3", "A computer Portal");

        // Print the HashMap
        System.out.println("HashMap: " + hashMap);

        // construct a new TreeMap from HashMap
        Map<String, String> treeMap = convertToTreeMap(hashMap);

        // Print the TreeMap
        System.out.println("TreeMap: " + treeMap);
    }
}
```

**输出:**

```java
HashMap: {1=Geeks, 2=forGeeks, 3=A computer Portal}
TreeMap: {1=Geeks, 2=forGeeks, 3=A computer Portal}
```

**3。使用谷歌的番石榴库**:番石榴还提供了一个树形图实现，可以用来创建一个空的树形图实例。

**算法:**

1.  获取要转换的 HashMap。
2.  使用番石榴库的 Maps.newTreeMap()创建新的树图
3.  将 hashMap 传递给 treeMap 的 putAll()方法
4.  返回形成的**树形图**

**程序:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert
// HashMap to TreeMap in Java 8

import com.google.common.collect.*;
import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to construct a
    // new TreeMap from HashMap
    public static <K extends Comparable, V> Map<K, V> 
                       convertToTreeMap(Map<K, V> hashMap)
    {
        // Create a new TreeMap
        Map<K, V> treeMap = Maps.newTreeMap();

        // Pass the hashMap to putAll() method
        treeMap.putAll(hashMap);

        // Return the TreeMap
        return treeMap;
    }

    public static void main(String args[])
    {
        // Create a HashMap
        Map<String, String> hashMap = new HashMap<>();

        // Add entries to the HashMap
        hashMap.put("1", "Geeks");
        hashMap.put("2", "forGeeks");
        hashMap.put("3", "A computer Portal");

        // Print the HashMap
        System.out.println("HashMap: " + hashMap);

        // construct a new TreeMap from HashMap
        Map<String, String> treeMap = convertToTreeMap(hashMap);

        // Print the TreeMap
        System.out.println("TreeMap: " + treeMap);
    }
}
```

**输出:**

```java
HashMap: {1=Geeks, 2=forGeeks, 3=A computer Portal}
TreeMap: {1=Geeks, 2=forGeeks, 3=A computer Portal}
```

**4。不兼容类型之间的转换**:如果所需的树形图与 HashMap 的类型不同，可以使用该方法。在这种情况下，转换需要手动完成。

**算法**:

1.  获取要转换的 HashMap。
2.  创建新的树形图
3.  对于哈希表的每个条目:
    *   通过转换将键和值转换为所需的类型
    *   通过 treeMap 的 put()方法插入转换后的对
4.  返回形成的**树形图**

**程序:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert
// HashMap to TreeMap in Java 8

import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to construct a new TreeMap from HashMap
    public static Map<Integer, String> 
               convertToTreeMap(Map<String, String> hashMap)
    {
        // Create a new TreeMap
        Map<Integer, String> treeMap = new TreeMap<>();

        // Convert the HashMap to TreeMap manually
        for (Map.Entry<String, String> e : hashMap.entrySet()) {
            treeMap.put(Integer.parseInt(e.getKey()), e.getValue());
        }

        // Return the TreeMap
        return treeMap;
    }

    public static void main(String args[])
    {
        // Create a HashMap
        Map<String, String> hashMap = new HashMap<>();

        // Add entries to the HashMap
        hashMap.put("1", "Geeks");
        hashMap.put("2", "forGeeks");
        hashMap.put("3", "A computer Portal");

        // Print the HashMap
        System.out.println("HashMap: " + hashMap);

        // construct a new TreeMap<Integer, String>
        // from HashMap<String, String>
        Map<Integer, String> treeMap = convertToTreeMap(hashMap);

        // Print the TreeMap
        System.out.println("TreeMap: " + treeMap);
    }
}
```

**输出:**

```java
HashMap: {1=Geeks, 2=forGeeks, 3=A computer Portal}
TreeMap: {1=Geeks, 2=forGeeks, 3=A computer Portal}
```