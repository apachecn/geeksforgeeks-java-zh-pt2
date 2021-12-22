# Java 中的树形图克隆()方法，示例

> 原文:[https://www . geesforgeks . org/tree map-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-clone-method-in-java-with-examples/)

在 Java 中，treemap 类的 clone()方法用于返回所提到的 TreeMap 的浅拷贝。它只是创建了一个地图的副本。

```java
--> java.util Package
    --> TreeMap Class
        --> clone() Method 
```

**语法:**

```java
Tree_Map.clone()
```

**参数:**该方法不取任何参数。

**返回类型:**树形图的副本。

**示例 1:** 将字符串值映射到整数键

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate clone() method
// of TreeMap class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty TreeMap by
        // declaring object of integer-string pairs
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        // using put() method
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // rinting all elements of TreeMap
        System.out.println("Initial Mappings are: "
                           + tree_map);

        // Displaying the cloned TreeMap
        // using clone()
        System.out.println("The cloned map look like this: "
                           + tree_map.clone());
    }
}
```

**Output**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The cloned map look like this: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
```

**示例 2:** 将整数值映射到字符串键

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program  to Illustrate clone() Method
// of TreeMap class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty TreeMap
        TreeMap<String, Integer> tree_map
            = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        // using put() method
        tree_map.put("Geeks", 10);
        tree_map.put("4", 15);
        tree_map.put("Geeks", 20);
        tree_map.put("Welcomes", 25);
        tree_map.put("You", 30);

        // Displaying all elements initial mapping TreeMap
        System.out.println("Initial Mappings are: "
                           + tree_map);

        // Displaying the cloned TreeMap
        // using clone()
        System.out.println("The cloned map look like this: "
                           + tree_map.clone());
    }
}
```

**Output**

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The cloned map look like this: {4=15, Geeks=20, Welcomes=25, You=30}
```

> **注意:**类似地，相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。