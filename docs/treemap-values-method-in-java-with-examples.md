# Java 中的 TreeMap 值()方法，带示例

> 原文:[https://www . geesforgeks . org/tree map-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-values-method-in-java-with-examples/)

在 Java 中，[树地图类](https://www.geeksforgeeks.org/treemap-in-java/)的*值()方法*存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中，该包用于从地图的值中创建集合。它基本上返回树图中值的集合视图。

```java
--> java.util package
    --> TreeMap class
        --> values() Method  
```

**语法:**

```java
Tree_Map.values()
```

**返回类型:**包含地图所有值的集合视图。

现在我们将提出不同的集合来说明下面列出的 values()方法:

1.  将字符串值映射到整数键
2.  将整数值映射到字符串键

**示例 1:** 将字符串值映射到整数键

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate values() Method
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
        System.out.println("Initial Mappings are: "
                           + tree_map);

        // Getting the set view of values
        // using values() method
        System.out.println("The collection is: "
                           + tree_map.values());
    }
}
```

**Output:** 

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The collection is: [Geeks, 4, Geeks, Welcomes, You]
```

**示例 2:** 将整数值映射到字符串键。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate values() method
// of TreeMap class

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
        System.out.println("Initial Mappings are: "
                           + tree_map);

        // Getting the set view of values
        // using values() method
        System.out.println("The collection is: "
                           + tree_map.values());
    }
}
```

**Output:** 

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The collection is: [15, 20, 25, 30]
```

> **注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。