# Java 中的 TreeMap headMap()方法

> 原文:[https://www . geesforgeks . org/tree map-hean map-method-in-Java/](https://www.geeksforgeeks.org/treemap-headmap-method-in-java/)

TreeMap 类的 Java . util . tree map . hear map(*key _ point*)方法用于获取严格小于参数 key_value 的所有对或部分映射。上述参数不包括在新准备的树形图中。由于集合由地图支持，因此对地图的任何更改都会反映在其他地图中，反之亦然。

**语法:**

```java
sorted_map = old_treemap.headMap(*key_point*)
```

**参数:**该方法取树形图中取的键类型的一个参数 *key_point* ，并引用该点，直到返回键值对。

**返回值:**该方法返回树图中键严格小于 key_point 的部分。

**异常:**该方法抛出三种类型的异常:

*   *ClassCastException:* 当 key_point 与 maps 比较器不兼容或不可比时，将引发此异常。
*   *NullPointRexception:*当关键点为空时引发此异常。
*   *IllegalArgumentException:*当 key_point 超出范围或超出地图范围限制时，会引发此异常。

下面的程序举例说明了 Java . util . treemap . hear map()方法的使用:
**程序 1:**

```java
// Java code to illustrate the get() method
import java.util.*;

public class Tree_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<Integer, String> tree_map = new 
                     TreeMap<Integer, String>();

        // Mapping string values to int keys
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Displaying the TreeMap
        System.out.println("Initial Tree is: " + 
                                       tree_map);

        // Creating the sorted map for map head
        SortedMap<Integer, String> map_head = new 
                       TreeMap<Integer, String>();
        map_head = tree_map.headMap(20);

        // Getting the map head
        System.out.println("The headmap is: " + map_head);
    }
}
```

**Output:**

```java
Initial Tree is: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The headmap is: {10=Geeks, 15=4}

```

**程序 2:**

```java
// Java code to illustrate the get() method
import java.util.*;

public class Tree_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<String, Integer> tree_map = new 
                      TreeMap<String, Integer>();

        // Mapping int values to string keys
        tree_map.put("Geeks", 10);
        tree_map.put("4", 15);
        tree_map.put("Geeks", 20);
        tree_map.put("Welcomes", 25);
        tree_map.put("You", 30);

        // Displaying the TreeMap
        System.out.println("Initial Tree is: " + 
                                       tree_map);

        // Creating the sorted map for map head
        SortedMap<String, Integer> map_head = new 
                       TreeMap<String, Integer>();
        map_head = tree_map.headMap("You");

        // Getting the map head
        System.out.println("The headmap is: " +
                                      map_head);
    }
}
```

**Output:**

```java
Initial Tree is: {4=15, Geeks=20, Welcomes=25, You=30}
The headmap is: {4=15, Geeks=20, Welcomes=25}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。