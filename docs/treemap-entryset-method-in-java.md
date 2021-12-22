# Java 中的 TreeMap entrySet()方法

> 原文:[https://www . geesforgeks . org/tree map-entryset-method-in-Java/](https://www.geeksforgeeks.org/treemap-entryset-method-in-java/)

java 中的 java.util.TreeMap.entrySet()方法用于创建一组包含在 TreeMap 中的相同元素。它基本上返回树图的集合视图，或者我们可以创建一个新的集合并将地图元素存储到其中。

**语法:**

```
tree_map.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与树形图元素相同的集合。

下面的程序用来说明 java.util.TreeMap.entrySet()方法:
**程序 1:** 将字符串值映射为整数键。

```
// Java code to illustrate the entrySet() method
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

        // Using entrySet() to get the set view
        System.out.println("The set is: " + tree_map.entrySet());
    }
}
```

**Output:**

```
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The set is: [10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You]

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the entrySet() method
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

        // Using entrySet() to get the set view
        System.out.println("The set is: " + tree_map.entrySet());
    }
}
```

**Output:**

```
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The set is: [4=15, Geeks=20, Welcomes=25, You=30]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。