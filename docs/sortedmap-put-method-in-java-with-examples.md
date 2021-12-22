# Java 中 SortedMap put()方法示例

> 原文:[https://www . geeksforgeeks . org/sorted map-put-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-put-method-in-java-with-examples/)

Java 中 [SortedMap 接口](https://www.geeksforgeeks.org/sortedmap-java-examples/)的 **put(** )方法用于将指定的值与该映射中的指定键相关联。

**语法:**

```
V put(K key,
    V value)
```

**参数:**此方法有两个参数:

*   **key** : left parameter,
*   **value** : the corresponding value of this key in the map.

**返回:**该方法返回**与该键关联的上一个值**(如果存在)，否则返回-1。

**注**:sorted Map 中的 put()方法继承了 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)。

下面的程序说明了 int put()方法的实现:

**程序 1:**

```
// Java code to show the implementation of
// put method in SortedMap interface

import java.util.*;

public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a SortedMap
        SortedMap<Integer, String> map
            = new TreeMap<>();

        map.put(1, "One");
        map.put(3, "Three");
        map.put(5, "Five");
        map.put(7, "Seven");
        map.put(9, "Ninde");

        System.out.println(map);
    }
}
```

**输出:**

```
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}

```

**程序 2:** 下面是展示 put()实现的代码。

```
// Java code to show the implementation of
// put method in SortedMap interface

import java.util.*;

public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a SortedMap
        SortedMap<String, String> map
            = new TreeMap<>();

        map.put("1", "One");
        map.put("3", "Three");
        map.put("5", "Five");
        map.put("7", "Seven");
        map.put("9", "Ninde");

        System.out.println(map);
    }
}
```

**输出:**

```
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # put(K，%20V)](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#put(K, %20V))