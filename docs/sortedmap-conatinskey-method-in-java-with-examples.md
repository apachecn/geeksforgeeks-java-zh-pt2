# 用示例排序 Java 中的 Map conatinsKey()方法

> 原文:[https://www . geeksforgeeks . org/sorted map-conatinskey-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-conatinskey-method-in-java-with-examples/)

**containsKey()** 方法用于检查特定的键是否被映射到 [SortedMap](https://www.geeksforgeeks.org/sortedmap-java-examples/) 中。它将关键元素作为参数，如果该元素在映射中被映射，则返回 True。

**语法:**

```java
boolean containsKey(*key_element*)
```

**参数:**该方法只取一个参数 *key_element* ，该参数是指其映射应该在 SortedMap 中检查的键。

**返回值:**如果检测到钥匙存在，则该方法返回**布尔值**为真，否则返回假。

**注**:在 [SortedMap](https://www.geeksforgeeks.org/sortedmap-java-examples/) 中的 containsKey()方法是从 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)继承而来的。

下面的程序用来说明 containsKey()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate
// the containsKey() method

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

        // Displaying the SortedMap
        System.out.println(
            "Initial Mappings are: "
            + map);

        // Checking for the key_element '20'
        System.out.println("Is the key '20' present? "
                           + map.containsKey(20));

        // Checking for the key_element '5'
        System.out.println("Is the key '5' present? "
                           + map.containsKey(5));
    }
}
```

**输出:**

```java
Initial Mappings are:
 {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Is the key '20' present? true
Is the key '5' present? false

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate
// the containsKey() method

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

        // Displaying the Map
        System.out.println(
            "Initial Mappings are: "
            + map);

        // Checking for the key_element 'Welcomes'
        System.out.println(
            "Is the key 'Welcomes' present? "
            + map.containsKey("Welcomes"));

        // Checking for the key_element 'World'
        System.out.println(
            "Is the key 'World' present? "
            + map.containsKey("World"));
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
Is the key 'Welcomes' present? true
Is the key 'World' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # contains key(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#containsKey(java.lang.Object))