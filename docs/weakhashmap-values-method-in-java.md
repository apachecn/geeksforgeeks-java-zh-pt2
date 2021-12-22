# Java 中的 WeakHashMap 值()方法

> 原文:[https://www . geeksforgeeks . org/weakashmap-values-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-values-method-in-java/)

java 中 HashMap 类的 java.util.WeakHashMap.values()方法用于从映射的值中创建一个集合。它基本上返回地图中值的集合视图。

**语法:**

```
Weak_Hash_Map.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

下面的程序用来说明 java.util.WeakHashMap.values()方法:
**程序 1:**

```
// Java code to illustrate the values() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<Integer, String> weak_hash = new 
                     WeakHashMap<Integer, String>();

        // Mapping string values to int keys
        weak_hash.put(10, "Geeks");
        weak_hash.put(15, "4");
        weak_hash.put(20, "Geeks");
        weak_hash.put(25, "Welcomes");
        weak_hash.put(30, "You");

        // Displaying the WeakHashMap
        System.out.println("Initial Mappings are: " + 
                                          weak_hash);

        // Using values() to get the set view of values
        System.out.println("The collection is: " + 
                                   weak_hash.values());
    }
}
```

**Output:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
The collection is: [You, 4, Geeks, Welcomes, Geeks]

```

**程序 2:**

```
// Java code to illustrate the values() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<String, Integer> weak_hash = new 
                     WeakHashMap<String, Integer>();

        // Mapping int values to string keys
        weak_hash.put("Geeks", 10);
        weak_hash.put("4", 15);
        weak_hash.put("Geeks", 20);
        weak_hash.put("Welcomes", 25);
        weak_hash.put("You", 30);

        // Displaying the WeakHashMap
        System.out.println("Initial Mappings are: " + 
                                          weak_hash);

        // Using values() to get the set view of values
        System.out.println("The collection is: " + 
                                   weak_hash.values());
    }
}
```

**Output:**

```
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
The collection is: [25, 15, 30, 20]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。