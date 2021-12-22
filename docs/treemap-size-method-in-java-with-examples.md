# Java 中的树形图大小()方法，示例

> 原文:[https://www . geesforgeks . org/tree map-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-size-method-in-java-with-examples/)

***【大小】()方法*** [***树状图类***](https://www.geeksforgeeks.org/treemap-in-java/) 用于获取地图的大小，即地图中键值对或映射的数量。

```java
--> java.util package
    --> TreeMap class
        --> size() Method   
```

**语法:**

```java
Tree_Map.size()
```

**返回值:**地图的大小，也就是地图中存在的键值对的数量。

**示例 1:** 将字符串值映射到整数键

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate size() Method
// of TreeMap class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty TreeMap by
        // declaring object of Integer, string pairs
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        // using put() method
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Displaying the elements of TreeMap
        System.out.println("Initial Mappings are: "
                           + tree_map);

        // Now displaying the size of this map
        // using size() method
        System.out.println("The size of the map is "
                           + tree_map.size());
    }
}
```

**Output:** 

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The size of the map is 5
```

**示例 2:** 将整数值映射到字符串键

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate the size() method
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

        // Printing the size of the map
        // using size() method
        System.out.println("The size of the map is "
                           + tree_map.size());
    }
}
```

**Output:** 

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The size of the map is 4
```

> **注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。