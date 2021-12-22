# 树形图包含 Java 中的 Key()方法

> 原文:[https://www . geesforgeks . org/tree map-contains key-method-in-Java/](https://www.geeksforgeeks.org/treemap-containskey-method-in-java/)

java.util.TreeMap.containsKey()方法用于检查特定的键是否在 TreeMap 中被映射。它将关键元素作为参数，如果该元素在映射中被映射，则返回 True。

**语法:**

```java
Tree_Map.containsKey(*key_element*)
```

**参数:**该方法只取一个参数 *key_element* ，该参数是指映射应该在地图内部检查的键。

**返回值:**如果检测到键的存在，则该方法返回布尔值 true，否则返回 false。

下面的程序用来说明 java.util.TreeMap.containsKey()方法:
**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the containsKey() method
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

        // Checking for the key_element '20'
        System.out.println("Is the key '20' present? " + 
        tree_map.containsKey(20));

        // Checking for the key_element '5'
        System.out.println("Is the key '5' present? " + 
        tree_map.containsKey(5));
    }
}
```

**Output:**

```java
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
Is the key '20' present? true
Is the key '5' present? false

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the containsKey() method
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
        System.out.println("Initial Mappings are: " + tree_map);

        // Checking for the key_element 'Welcomes'
        System.out.println("Is the key 'Welcomes' present? " + 
        tree_map.containsKey("Welcomes"));

        // Checking for the key_element 'World'
        System.out.println("Is the key 'World' present? " + 
        tree_map.containsKey("World"));
    }
}
```

**Output:**

```java
Initial Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
Is the key 'Welcomes' present? true
Is the key 'World' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。