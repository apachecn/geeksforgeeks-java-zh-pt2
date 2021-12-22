# Java 中 SortedMap remove()方法，示例

> 原文:[https://www . geesforgeks . org/sorted map-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-remove-method-in-java-with-examples/)

Java 中 [SortedMap 接口](https://www.geeksforgeeks.org/sortedmap-java-examples/)的 **remove()** 方法用于从该地图中移除一个键的映射(如果该键存在于地图中)。

**语法:**

```java
V remove(Object key)
```

**参数:**此方法只有一个参数**键**，其映射将从地图中移除。

**返回:**该方法返回该**排序地图**先前与该关键字相关联的值，如果排序地图不包含该关键字的映射，则返回空值。

**注**:sorted Map 中的 remove()方法继承了 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)。

下面的程序说明了 remove()方法的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show the implementation of
// remove method in SortedMap interface

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
        map.put(9, "Nine");
        System.out.println(map);

        map.remove(3);

        System.out.println(map);

        // If it doesn't exists, returns
        // null and does not affects the map
        map.remove(2);

        System.out.println(map);
    }
}
```

**Output:** 

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine}
{1=One, 5=Five, 7=Seven, 9=Nine}
{1=One, 5=Five, 7=Seven, 9=Nine}
```

**程序 2:** 下面是展示 remove()实现的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show the implementation of
// remove method in SortedMap interface

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
        map.put("9", "Nine");
        System.out.println(map);

        map.remove("3");

        System.out.println(map);
    }
}
```

**Output:** 

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine}
{1=One, 5=Five, 7=Seven, 9=Nine}
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # put(K，%20V)](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#put(K, %20V))