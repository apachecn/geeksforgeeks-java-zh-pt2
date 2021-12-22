# Java 中 SortedMap isEmpty()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted map-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-isempty-method-in-java-with-examples/)

Java 中 [**SortedMap 接口**](https://www.geeksforgeeks.org/sortedmap-java-examples/) 的 **isEmpty()** 方法用于检查一个映射是否有任何键和值对的条目。如果不存在映射，则返回 true。

**语法:**

```java
boolean isEmpty()
```

**参数:**这个方法没有参数。

**返回:**如果映射不包含任何键值映射，该方法返回**真**。

**注**:sorted Map 中的 isEmpty()方法继承了 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)

下面的程序展示了 int isEmpty()方法的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show the implementation of
// isEmpty method in SortedMap interface

import java.util.*;

public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a SortedMap
        SortedMap<String, String> map
            = new TreeMap<>();

        System.out.println(map);

        System.out.println(map.isEmpty());
    }
}
```

**Output:** 

```java
{}
true
```

**程序 2:** 下面是展示 isEmpty()实现的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show the implementation of
// isEmpty method in SortedMap interface

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

        System.out.println(map.isEmpty());
    }
}
```

**Output:** 

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}
false
```

**参考:**[https://docs . Oracle . com/javase/6/docs/API/Java/util/ArrayList . html #包含(java.lang.Object)](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))