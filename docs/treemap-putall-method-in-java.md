# Java 中的 TreeMap putAll()方法

> 原文:[https://www . geesforgeks . org/tree map-pull-method-in-Java/](https://www.geeksforgeeks.org/treemap-putall-method-in-java/)

java.util.TreeMap.putAll()是 TreeMap 类的一个内置方法，用于复制操作。该方法将所有元素(即映射)从一个映射复制到另一个映射。

**语法:**

```
new_tree_map.putAll(*exist_tree_map*)
```

**参数:**该方法取一个参数 *exist_tree_map* ，指的是我们要复制的现有地图。

**返回值:**该方法不返回值。

**异常:**该方法抛出两种类型的异常:

*   *NullPointRexception:*如果指定的映射为空或包含空键，并且该映射不允许或不持有空键，则会引发这种类型的异常。
*   *ClassCastException:* 如果指定的类的键或值与该映射不同，或者它阻止存储该映射，则会引发这种类型的异常。

下面的程序说明了 java.util.TreeMap.putAll()方法的工作原理:
**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the putAll() method
import java.util.*;

public class Tree_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<Integer, String> tree_map = 
                  new TreeMap<Integer, String>();

        // Mapping string values to int keys
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Displaying the TreeMap
        System.out.println("Initial Mappings are: " + tree_map);

        // Creating a new tree map and copying
        TreeMap<Integer, String> new_tree_map = 
                        new TreeMap<Integer, String>();
        new_tree_map.putAll(tree_map);

        // Displaying the final TreeMap
        System.out.println("The new map looks like this: "
                                            + new_tree_map);
    }
}
```

**Output:**

```
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The new map looks like this: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the putAll() method
import java.util.*;

public class Tree_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<String, Integer> tree_map = 
                    new TreeMap<String, Integer>();

        // Mapping int values to string keys
        tree_map.put("Geeks", 10);
        tree_map.put("4", 15);
        tree_map.put("Geeks", 20);
        tree_map.put("Welcomes", 25);
        tree_map.put("You", 30);

        // Displaying the TreeMap
        System.out.println("Initial Mappings are: "
                                         + tree_map);

        // Creating a new tree map and copying
        TreeMap<String, Integer> new_tree_map = 
                         new TreeMap<String, Integer>();
        new_tree_map.putAll(tree_map);

        // Displaying the final TreeMap
        System.out.println("The new map looks like this: " 
                                          + new_tree_map);
    }
}
```

**Output:**

```
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The new map looks like this: {4=15, Geeks=20, Welcomes=25, You=30}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。