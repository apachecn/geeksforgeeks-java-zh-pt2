# Java 中的 TreeMap clear()方法

> 原文:[https://www.geeksforgeeks.org/treemap-clear-method-in-java/](https://www.geeksforgeeks.org/treemap-clear-method-in-java/)

java 中的 java.util.TreeMap.clear()方法用于清除和移除指定 TreeMap 中的所有元素或映射。

**语法:**

```java
Tree_Map.clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

下面的程序用来说明 java.util.TreeMap.clear()的工作方式方法:
**程序 1:** 将字符串值映射为整数键。

```java
// Java code to illustrate the clear() method
import java.util.*;

public class Tree_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<Integer, String> tree_map = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Displaying the TreeMap
        System.out.println("Initial Mappings are: " + tree_map);

        // Clearing the tree map using clear()
        tree_map.clear();

        // Displaying the final TreeMap
        System.out.println("Finally the map looks like: " + tree_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Finally the map looks like this: {}

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the clear() method
import java.util.*;

public class Tree_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<String, Integer> tree_map = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        tree_map.put("Geeks", 10);
        tree_map.put("4", 15);
        tree_map.put("Geeks", 20);
        tree_map.put("Welcomes", 25);
        tree_map.put("You", 30);

        // Displaying the TreeMap
        System.out.println("Initial Mappings are: " + tree_map);

        // Clearing the tree map using clear()
        tree_map.clear();

        // Displaying the final TreeMap
        System.out.println("Finally the map looks like: " + tree_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
Finally the map looks like: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。