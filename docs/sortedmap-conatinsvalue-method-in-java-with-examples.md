# Java 中 SortedMap conatinsValue()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted map-conatinsvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-conatinsvalue-method-in-java-with-examples/)

**containsValue()** 方法用于检查特定值是由 SortedMap 中的单个还是多个键映射的。它将该值作为参数，如果该值由映射中的任何键映射，则返回 True。

**语法:**

```
boolean containsValue(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由映射内任何键检查的值。

**返回值:**如果检测到值的映射，则该方法返回**布尔值**为真，否则返回假。

**注意**:在 [SortedMap](https://www.geeksforgeeks.org/sortedmap-java-examples/) 中的 containsValue()方法是从 Java 中的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)继承而来的。

下面的程序说明了 containsValue()方法:

**程序 1:** 将字符串值映射到整数键。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// the containsValue() method

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

        // Checking for the Value 'Geeks'
        System.out.println(
            "Is the value 'Geeks' present? "
            + map.containsValue("Geeks"));

        // Checking for the Value 'World'
        System.out.println(
            "Is the value 'World' present? "
            + map.containsValue("World"));
    }
}
```

**Output:** 

```
Initial Mappings are:
 {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Is the value 'Geeks' present? true
Is the value 'World' present? false
```

**程序 2:** 将整数值映射到字符串键。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// the containsValue() method

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

        // Checking for the Value '10'
        System.out.println(
            "Is the value '10' present? "
            + map.containsValue(10));

        // Checking for the Value '30'
        System.out.println(
            "Is the value '30' present? "
            + map.containsValue(30));

        // Checking for the Value '40'
        System.out.println(
            "Is the value '40' present? "
            + map.containsValue(40));
    }
}
```

**Output:** 

```
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
Is the value '10' present? false
Is the value '30' present? true
Is the value '40' present? false
```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。
**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # contains value(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#containsValue(java.lang.Object))