# Java 中 SortedMap entrySet()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted map-entryset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-entryset-method-in-java-with-examples/)

Java 中 **SortedMap 接口的 **entrySet()方法**用于创建一组包含在地图中的相同元素。它基本上返回地图的集合视图，或者创建一个新的集合并将地图元素存储到其中。**

**语法:**

```
SortedMap.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与地图元素相同的集合。

下面的程序用来说明上述方法的工作原理:

**程序 1:** 使用 HashMap。

```
// Java code to illustrate the entrySet() method

import java.util.*;

public class SortedMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        SortedMap<String, Integer>
            sotree_map = new TreeMap<String,
                                     Integer>();

        // Mapping int values to string keys
        sotree_map.put("Geeks", 10);
        sotree_map.put("4", 15);
        sotree_map.put("Geeks", 20);
        sotree_map.put("Welcomes", 25);
        sotree_map.put("You", 30);

        // Displaying the TreeMap
        System.out.println("Initial Mappings are: "
                           + sotree_map);

        // Using entrySet() to get the set view
        System.out.println("The set is: "
                           + sotree_map.entrySet());
    }
}
```

**节目 2:**

```
// Java code to illustrate the entrySet() method

import java.util.*;

public class SortedMap_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        SortedMap<Integer, String>
            sotree_map = new TreeMap<Integer,
                                     String>();

        // Mapping string values to int keys
        sotree_map.put(10, "Geeks");
        sotree_map.put(15, "4");
        sotree_map.put(20, "Geeks");
        sotree_map.put(25, "Welcomes");
        sotree_map.put(30, "You");

        // Displaying the TreeMap
        System.out.println("Initial Mappings are: "
                           + sotree_map);

        // Using entrySet() to get the set view
        System.out.println("The set is: "
                           + sotree_map.entrySet());
    }
}
```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。