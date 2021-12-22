# Java 中的 SortedMap headMap()方法

> 原文:[https://www . geesforgeks . org/sorted map-hean map-method-in-Java/](https://www.geeksforgeeks.org/sortedmap-headmap-method-in-java/)

Java 中 **SortedMap 接口的 toKey()方法用于返回该地图中键严格小于 Tokey 的部分的视图。**

***   The map returned by this method is backed by this map, so the changes of the returned map will be reflected in this map, and vice versa.*   The map returned by this method supports all optional map operations supported by the map.**

**注意**:如果试图插入一个超出其范围的键，这个方法返回的地图将抛出一个 IllegalArgumentException。

**语法** :

```
SortedMap<K, V> headMap(K toKey)

```

其中，K 是该集合维护的键的类型，V 是与该键相关联的值的类型。

**参数**:该函数接受单个参数 *toKey* ，该参数代表返回地图中关键点的高端点(不包括)。

**返回值**:返回该地图关键点严格小于 toKey 的部分的视图。

**异常**:

*   [T0】 class castexception 【T1]: If the parameter *toKey* is not compatible with the comparator of this map (or if the map has no comparator, if Tokey does not implement compatible).
*   **Null pointer exception** : If the parameter *tokey* is null and the mapping does not allow null keys.
*   [T0】 IllegalArgumentException 【T1]: If the map itself has a restricted range and toKey is outside the boundary of the range,

下面的程序说明了上述方法:

**程序 1** :

```
// A Java program to demonstrate
// working of SortedSet
import java.util.*;

public class Main {
    public static void main(String[] args)
    {
        // Create a TreeSet and inserting elements
        SortedMap<Integer, String> mp = new TreeMap<>();

        // Adding Element to SortedSet
        mp.put(1, "One");
        mp.put(2, "Two");
        mp.put(3, "Three");
        mp.put(4, "Four");
        mp.put(5, "Five");

        // Returning the map with key less than 3
        System.out.print("Last Key in the map is : "
                         + mp.headMap(3));
    }
}
```

**输出:**

```
Last Key in the map is : {1=One, 2=Two}

```

**程序二** :

```
// A Java program to demonstrate
// working of SortedSet
import java.util.*;

public class Main {
    public static void main(String[] args)
    {
        // Create a TreeSet and inserting elements
        SortedMap<String, String> mp = new TreeMap<>();

        // Adding Element to SortedSet
        mp.put("One", "Geeks");
        mp.put("Two", "For");
        mp.put("Three", "Geeks");
        mp.put("Four", "Code");
        mp.put("Five", "It");

        // Returning map with key less than H
        System.out.print("Last Key in the map is : "
                         + mp.headMap("H"));
    }
}
```

**输出:**

```
Last Key in the map is : {Five=It, Four=Code}

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/sorted map . html #头标(K)](https://docs.oracle.com/javase/10/docs/api/java/util/SortedMap.html#headMap(K))