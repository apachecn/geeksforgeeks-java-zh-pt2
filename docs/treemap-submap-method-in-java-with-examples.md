# Java 中的 TreeMap subMap()方法，带示例

> 原文:[https://www . geesforgeks . org/tree map-submap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-submap-method-in-java-with-examples/)

在 Java 中， [TreeMap 类](https://www.geeksforgeeks.org/treemap-in-java/)的 subMap()方法用于返回参数中指定范围的键定义的地图的一部分或多个部分。在一个或另一个地图中所做的任何更改都将反映另一个地图中的更改。

**语法:**

```java
Tree_Map.subMap(*K startKey, K endKey*)
```

**参数:**该方法取 Key 类型的两个参数:

*   地图的起点或下端，包括要考虑的点。(开始键)
*   地图的端点或高端，不包括要考虑的点。(*结束键*)

**返回类型:**该方法返回另一个包含指定范围内地图的一部分或多个部分的地图。

**异常:**该方法抛出三种类型的异常:

*   [*class castexception:*](https://www.geeksforgeeks.org/how-to-solve-class-cast-exceptions-in-java/)如果方法中提到的参数无法与此地图的关键点进行比较，则会引发此异常。
*   [*【NullPointRexception:*](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)如果任一参数为空类型且映射不接受任何空值，则会引发此异常。
*   [*【IllegalArgumentException:*](https://www.geeksforgeeks.org/how-to-solve-illegalargumentexception-in-java/)如果上述参数超出范围或下限大于上限，则抛出此异常。

> **注意:**如果开始键等于结束键，则返回空映射。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the subMap() method
// of TreeMap class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeMap by
        // declaring object of integer, string pairs
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        // using put() method
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Printing the elements of TreeMap
        System.out.println("The original map is: "
                           + tree_map);

        // Displaying the submap
        // using subMap() method
        System.out.println("The subMap is "
                           + tree_map.subMap(15, 30));
    }
}
```

**Output:** 

```java
The original map is: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The subMap is {15=4, 20=Geeks, 25=Welcomes}
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate the subMap() method

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty TreeMap by
        // declaring object of string, integer pairs
        TreeMap<String, Integer> tree_map
            = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        // using put() method
        tree_map.put("Geeks", 10);
        tree_map.put("4", 15);
        tree_map.put("Geeks", 20);
        tree_map.put("Welcomes", 25);
        tree_map.put("You", 30);

        // Printing the elements of TreeMap
        System.out.println("The original map is: "
                           + tree_map);

        // Displaying the subMap
        // using subMap() method
        System.out.println(
            "The subMap is "
            + tree_map.subMap("Geeks", "Geeks"));
    }
}
```

**Output:** 

```java
The original map is: {4=15, Geeks=20, Welcomes=25, You=30}
The subMap is {}
```