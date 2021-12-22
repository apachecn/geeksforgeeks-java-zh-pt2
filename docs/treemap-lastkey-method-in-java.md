# Java 中的 TreeMap lastKey()方法

> 原文:[https://www . geesforgeks . org/tree map-last key-method-in-Java/](https://www.geeksforgeeks.org/treemap-lastkey-method-in-java/)

java.util.TreeMap.lastKey()用于检索地图中最后或最高的键。

**语法:**

```
 tree_map.lastKey()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回地图中出现的最后一个键。

**异常:**如果地图为空，该方法抛出*nosucheelementexception*。

下面的程序说明了 java.util.TreeMap.lastKey()方法的工作:
**程序 1:**

```
// Java code to illustrate the lastKey() method
import java.util.*;

public class Tree_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<Integer, String> tree_map = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Displaying the TreeMap
        System.out.println("The Mappings are: " + tree_map);

        // Displaying the lastKey of the map
        System.out.println("The last key is " + tree_map.lastKey());
    }
}
```

**Output:**

```
The Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The last key is 30

```

**程序 2:**

```
// Java code to illustrate the lastKey() method
import java.util.*;

public class Tree_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<String, Integer> tree_map = new TreeMap<String, Integer>();

        // Mapping int values to string keys
        tree_map.put("Geeks", 10);
        tree_map.put("4", 15);
        tree_map.put("Geeks", 20);
        tree_map.put("Welcomes", 25);
        tree_map.put("You", 30);

        // Displaying the TreeMap
        System.out.println("The Mappings are: " + tree_map);

        // Displaying the lastKey of the map
        System.out.println("The last key is " + tree_map.lastKey());
    }
}
```

**Output:**

```
The Mappings are: {4=15, Geeks=20, Welcomes=25, You=30}
The last key is You

```