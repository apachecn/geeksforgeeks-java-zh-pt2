# Java 中 SortedMap values()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted map-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-values-method-in-java-with-examples/)

Java 中 **SortedMap 界面**的**值()方法**用于创建地图值的集合。它基本上返回地图中值的集合视图。

**语法:**

```
SortedMap.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

下面的程序用来说明上述方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the values() method

import java.util.*;

public class SortedMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        SortedMap<Integer, String>
            sotree_map = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        sotree_map.put(10, "Geeks");
        sotree_map.put(15, "4");
        sotree_map.put(20, "Geeks");
        sotree_map.put(25, "Welcomes");
        sotree_map.put(30, "You");

        // Displaying the TreeMap
        System.out.println("Initial Mappings are: "
                           + sotree_map);

        // Using values() to get the set view of values
        System.out.println("The collection is: "
                           + sotree_map.values());
    }
}
```

**输出:**

```
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The collection is: [Geeks, 4, Geeks, Welcomes, You]

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the values() method

import java.util.*;

public class SortedMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        SortedMap<String, Integer>
            sotree_map = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        sotree_map.put("Geeks", 10);
        sotree_map.put("4", 15);
        sotree_map.put("Geeks", 20);
        sotree_map.put("Welcomes", 25);
        sotree_map.put("You", 30);

        // Displaying the TreeMap
        System.out.println("Initial Mappings are: "
                           + sotree_map);

        // Using values() to get the set view of values
        System.out.println("The collection is: "
                           + sotree_map.values());
    }
}
```

**输出:**

```
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The collection is: [15, 20, 25, 30]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。