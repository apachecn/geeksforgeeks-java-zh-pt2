# Java 中 SortedMap hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted map-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-hashcode-method-in-java-with-examples/)

Java 中 [SortedMap 接口](https://www.geeksforgeeks.org/sortedmap-java-examples/)的 **hashCode()** 方法用于为给定的包含键和值的映射生成 hashCode。

**语法:**

```
int hashCode()
```

**参数:**这个方法没有参数。

**返回:**该方法返回给定地图的 hashCode 值。

**注**:在 [SortedMap](https://www.geeksforgeeks.org/sortedmap-java-examples/) 中的 hashCode()方法继承了 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)。

下面的程序展示了 int hashCode()方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// hashCode() method in SortedMap interface

import java.util.*;

public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a SortedMap
        // of type TreeMap
        SortedMap<Integer, String> map
            = new TreeMap<>();

        map.put(1, "One");
        map.put(3, "Three");
        map.put(5, "Five");
        map.put(7, "Seven");
        map.put(9, "Ninde");
        System.out.println(map);

        int hash = map.hashCode();

        System.out.println(hash);
    }
}
```

**输出:**

```
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}
238105666

```

**程序 2:** 下面是展示 hashCode()实现的代码。

```
// Java code to show the implementation of
// hashCode method in SortedMap interface

import java.util.*;

public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a SortedMap
        // of type TreeMap
        SortedMap<String, String> map
            = new TreeMap<>();

        map.put("1", "One");
        map.put("3", "Three");
        map.put("5", "Five");
        map.put("7", "Seven");
        map.put("9", "Ninde");
        System.out.println(map);

        int hash = map.hashCode();

        System.out.println(hash);
    }
}
```

**输出:**

```
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}
238105618

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))