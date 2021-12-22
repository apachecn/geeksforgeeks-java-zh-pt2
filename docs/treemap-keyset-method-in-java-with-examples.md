# Java 中的树形图键集()方法，示例

> 原文:[https://www . geesforgeks . org/tree map-key set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-keyset-method-in-java-with-examples/)

在 Java 中，[树形图类](https://www.geeksforgeeks.org/treemap-in-java/)的 *keySet()方法*存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中，用于创建一组包含在树形图中的关键元素。它基本上返回一个键的集合视图，或者我们可以创建一个新的集合，并将键元素以升序存储在其中。由于集合由地图支持，因此对地图所做的任何更改都会反映在集合中，反之亦然。

```java
--> java.util Package
    --> TreeMap Class
        --> keySet() Method  
```

**语法:**

```java
tree_map.keySet()
```

**返回类型:**以升序排列树图的键的集合。

**示例 1:** 将字符串值映射到整数键。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the keySet() method
// of TreeMap class where we are
// Mapping String Values to Integer Keys

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // MAin driver method
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

        // Printing the elements of above TreeMap
        System.out.println("Initial Mappings are: "
                           + tree_map);

        // Getting the set view of keys
        // using keySet() method
        System.out.println("The set is: "
                           + tree_map.keySet());
    }
}
```

**Output:** 

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The set is: [10, 15, 20, 25, 30]
```

**示例 2:** 将整数值映射到字符串键

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate keySet() Method
// of TreeMap class where we are
// Mapping Integer Values to String Keys

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

        // Getting the set view of keys
        // using keySet() method
        System.out.println("The set is: "
                           + tree_map.keySet());
    }
}
```

**Output:** 

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The set is: [4, Geeks, Welcomes, You]
```

> **注意:**类似地，相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。