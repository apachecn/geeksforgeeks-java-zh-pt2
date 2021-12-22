# Java 中的 SortedMap keySet()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted map-key set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-keyset-method-in-java-with-examples/)

Java 中 **SortedMap 接口**的 **keySet()方法**用于创建一组包含在树图中的关键元素。它基本上返回一个键的集合视图，或者我们可以创建一个新的集合，并以升序存储其中的键元素。由于集合由地图支持，因此对地图所做的任何更改都会反映在集合中，反之亦然。

**语法:**

```
SortedMap.keySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以升序返回一个具有树图键的集合。

下面的程序用来说明上述方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the keySet() method

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

        // Using keySet() to get the set view of keys
        System.out.println("The set is: "
                           + sotree_map.keySet());
    }
}
```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the keySet() method

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

        // Using keySet() to get the set view of keys
        System.out.println("The set is: "
                           + sotree_map.keySet());
    }
}
```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。