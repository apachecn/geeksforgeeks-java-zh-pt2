# Java 中的 TreeMap lastEntry()方法，带示例

> 原文:[https://www . geesforgeks . org/tree map-last entry-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-lastentry-method-in-java-with-examples/)

Java . util . treemap . LastEntry(**)**方法用于返回与此映射中最大键相关联的键值映射，如果映射为空，则返回 null。

**语法:**

```java
tree_map.lastEntry()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回具有最大键的条目，如果该映射为空，则返回空。

下面的例子说明了 java.util.TreeMap.lastEntry()方法的工作原理:

**例 1:** 当地图不为空时。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// TreeMap lastEntry() method
import java.util.*;

class GFG {
    public static void main(String args[])
    {

        // Creating an empty TreeMap
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        tree_map.put(98, "Geeks");
        tree_map.put(100, "For");
        tree_map.put(103, "Geeks");

        // Printing last entry of the map
        System.out.println("The last entry is : "
                           + tree_map.lastEntry());
    }
}
```

**Output**

```java
The last entry is : 103=Geeks

```

**例 2:** 当地图为空时。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// TreeMap lastEntry() method
import java.util.*;

class GFG {
    public static void main(String args[])
    {

        // Creating an empty TreeMap
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>();

        // Printing last entry of the map
        System.out.println("The last entry is : "
                           + tree_map.lastEntry());
    }
}
```

**Output**

```java
The last entry is : null

```