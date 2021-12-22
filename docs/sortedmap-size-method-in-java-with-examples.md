# Java 中 SortedMap size()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted map-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-size-method-in-java-with-examples/)

Java 中 **[SortedMap 接口](https://www.geeksforgeeks.org/sortedmap-java-examples/)** 的 **size()** 方法用于获取 SortedMap 的大小，指的是 SortedMap 中键值对或映射的数量。

**语法:**

```
int size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回 SortedMap 的**大小**，这也意味着 SortedMap 中存在的键值对的数量。

**注**:sorted Map 中的 size()方法继承了 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)。

下面的程序说明了 size()方法的工作原理:

**程序 1** :将字符串值映射到整数键。

```
// Java code to illustrate the size() method

import java.util.*;

public class Gfg {
    public static void main(String[] args)
    {

        // Creating an empty SortedMap
        SortedMap<Integer, String> map
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        map.put(10, "Geeks");
        map.put(15, "4");
        map.put(20, "Geeks");
        map.put(25, "Welcomes");
        map.put(30, "You");

        // Displaying the SortedMap
        System.out.println(
            "Initial Mappings are: "
            + map);

        // Displaying the size of the map
        System.out.println(
            "The size of the map is "
            + map.size());
    }
}
```

**输出:**

```
Initial Mappings are:
 {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The size of the map is 5

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the size() method

import java.util.*;

public class Gfg {
    public static void main(String[] args)
    {

        // Creating an empty SortedMap
        SortedMap<String, Integer> map
            = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        map.put("Geeks", 10);
        map.put("4", 15);
        map.put("Geeks", 20);
        map.put("Welcomes", 25);
        map.put("You", 30);

        // Displaying the SortedMap
        System.out.println(
            "Initial Mappings are: "
            + map);

        // Displaying the size of the map
        System.out.println(
            "The size of the map is "
            + map.size());
    }
}
```

**输出:**

```
Initial Mappings are:
 {4=15, Geeks=20, Welcomes=25, You=30}
The size of the map is 4

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/map . html # size–](https://docs.oracle.com/javase/9/docs/api/java/util/Map.html#size--)