# Java 中 SortedMap putAll()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted map-putall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-putall-method-in-java-with-examples/)

Java 中 [SortedMap 接口](https://www.geeksforgeeks.org/sortedmap-java-examples/)的 **putAll()** 方法用于将指定 SortedMap 的所有映射复制到这个 SortedMap。

**语法:**

```java
void putAll(Map m)
```

**参数:**这个方法只有一个参数**映射 m** ，它包含要复制到给定 SortedMap 的键值映射。

**返回:**该方法返回**与该键关联的上一个值**(如果存在)，否则返回-1。

**注**:[sorted Map](https://www.geeksforgeeks.org/sortedmap-java-examples/)中的 putAll()方法继承了 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)。

下面的程序说明了 int putAll()方法的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show the implementation of
// putAll method in SortedMap interface

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

        SortedMap<Integer, String> mp
            = new TreeMap<>();

        mp.put(10, "Ten");
        mp.put(30, "Thirty");
        mp.put(50, "Fifty");

        map.putAll(mp);

        System.out.println(map);
    }
}
```

**Output:** 

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine}
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine, 10=Ten, 30=Thirty, 50=Fifty}
```

**程序 2:** 下面是显示 putAll()实现的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show the implementation of
// putAll method in SortedMap interface

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

        SortedMap<String, String> mp
            = new TreeMap<>();

        mp.put("10", "Ten");
        mp.put("30", "Thirty");
        mp.put("50", "Fifty");

        map.putAll(mp);

        System.out.println(map);
    }
}
```

**Output:** 

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine}
{1=One, 10=Ten, 3=Three, 30=Thirty, 5=Five, 50=Fifty, 7=Seven, 9=Nine}
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # put(K，%20V)](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#put(K, %20V))