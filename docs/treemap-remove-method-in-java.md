# Java 中的 TreeMap remove()方法

> 原文:[https://www . geesforgeks . org/tree map-remove-method-in-Java/](https://www.geeksforgeeks.org/treemap-remove-method-in-java/)

java.util.TreeMap.remove()是 TreeMap 类的内置方法，用于从映射中移除任何特定键的映射。它基本上删除了地图中任何特定键的值。

**语法:**

```java
Tree_Map.remove(*Object key*)
```

**参数:**该方法采用一个参数*键*，其映射将从地图中移除。

**返回值:**该方法返回之前映射到指定键的值，如果该键存在，则该方法返回空值。

下面的程序说明了 java.util.TreeMap.remove()方法的工作原理:
**程序 1:** 在传递现有密钥时。

```java
// Java code to illustrate the remove() method
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
        System.out.println("Initial Mappings are: " 
                                         + tree_map);

        // Removing the existing key mapping
        String returned_value = (String)tree_map.remove(20);

        // Verifying the returned value
        System.out.println("Returned value is: " +
                                        returned_value);

        // Displayin the new map
        System.out.println("New map is: " + tree_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Returned value is: Geeks
New map is: {10=Geeks, 15=4, 25=Welcomes, 30=You}

```

**程序 2:** 传递新密钥时。

```java
// Java code to illustrate the remove() method
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
        System.out.println("Initial Mappings are: " 
                                          + tree_map);

        // Removing the new key mapping
        // Note : 50 is not present and so null
        // should be returned (nothing to remove)
        String returned_value = (String)tree_map.remove(50);

        // Verifying the returned value
        System.out.println("Returned value is: " 
                                   + returned_value);

        // Displayin the new map
        System.out.println("New map is: " + tree_map);
    }
}
```

**Output:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Returned value is: null
New map is: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。