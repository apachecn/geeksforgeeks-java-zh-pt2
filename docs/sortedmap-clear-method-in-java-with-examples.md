# Java 中 SortedMap clear()方法，示例

> 原文:[https://www . geesforgeks . org/sorted map-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-clear-method-in-java-with-examples/)

[SortedMap Java](https://www.geeksforgeeks.org/sortedmap-java-examples/) 中的 **clear()** 方法用于清除和移除指定 SortedMap 集合中的所有元素或映射。

**语法:**

```java
void clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

**注**:[sorted Map](https://www.geeksforgeeks.org/sortedmap-java-examples/)中的 clear()方法继承了 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)。

以下程序用于说明 clear()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the clear() method

import java.util.*;

public class Map_Demo {
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

        // Displaying the Map
        System.out.println(
            "Initial Mappings are: "
            + map);

        // Clearing the sorted map using clear()
        map.clear();

        // Displaying the final SortedMap
        System.out.println(
            "Finally the maps"
            + " look like this: "
            + map);
    }
}
```

**输出:**

```java
Initial Mappings are:
 {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Finally the maps look like this: {}

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the clear() method

import java.util.*;

public class Map_Demo {
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

        // Clearing the SortedMap using clear()
        map.clear();

        // Displaying the final Map
        System.out.println(
            "Finally the maps "
            + "look like this: "
            + map);
    }
}
```

**输出:**

```java
Initial Mappings are:
 {4=15, Geeks=20, Welcomes=25, You=30}
Finally the maps look like this: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # clear()](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#clear())