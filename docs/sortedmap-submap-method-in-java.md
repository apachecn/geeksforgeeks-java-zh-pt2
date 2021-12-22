# Java 中的 SortedMap subMap()方法

> 原文:[https://www . geesforgeks . org/sorted map-submap-method-in-Java/](https://www.geeksforgeeks.org/sortedmap-submap-method-in-java/)

Java 中 **SortedMap 接口的 subMap()方法用于返回该地图的一部分的视图，该部分的关键点范围从*到*，包括该部分，到*到*，不包括该部分。**

***   The map returned by this method is backed by this map, so the change of the returned map is reflected in this map, and vice versa.*   The map returned by this method supports all optional map operations supported by the map.**

**注意**:如果试图在范围外插入一个键，这个方法返回的地图会抛出一个 IllegalArgumentException。

**语法** :

```
SortedMap<K, V> subMap(K fromKey,
                      K toKey)

```

其中，K 是该集合维护的键的类型，V 是与该键相关联的值的类型。

**参数**:该函数接受两个参数 *fromKey* 和 *toKey* ，分别代表返回地图中关键点的低端点(包含)和高端点(不包含)。

**返回值**:返回地图中从*到*再到*到*的部分。

**异常**:

*   [T0】 class castexception 【T1]: If the parameter *fromKey* is not compatible with the comparator of this map (or if the map has no comparator, if fromkey does not implement compatible).
*   **null pointer exception** : if the parameter *fromkey* is null, and the mapping does not allow null keys.
*   [T0】 IllegalArgumentException 【T1]: If the map itself has a restricted range, and *from key* is in the range.

的边界之外

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

        // Returning the key ranging
        // between 2 and 5
        System.out.print("Elements in range from 2 to 5 in the map is : "
                         + mp.subMap(2, 5));
    }
}
```

**输出:**

```
Elements in range from 2 to 5 in the map is : {2=Two, 3=Three, 4=Four}

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

        // Returning the key range between D and Z
        System.out.print("Key in range from D to Z in the map is : "
                         + mp.subMap("D", "Z"));
    }
}
```

**输出:**

```
Key in range from D to Z in the map is : {Five=It, Four=Code, One=Geeks, Three=Geeks, Two=For}

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/sortedmap . html # subMap(K)](https://docs.oracle.com/javase/10/docs/api/java/util/SortedMap.html#subMap(K))