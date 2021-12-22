# Java 中的 WeakHashMap putall()方法

> 原文:[https://www . geeksforgeeks . org/weakashmap-pull-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-putall-method-in-java/)

java.util.WeakHashMap.putAll()是 WeakHashMap 类的一个内置方法，用于复制操作。该方法将所有元素(即映射)从一个映射复制到另一个映射。

**语法:**

```
new_weakhash_map.putAll(*exist_weakhash_map*)
```

**参数:**该方法取一个参数 *exist_weakhash_map* ，指的是我们要复制的现有地图。

**返回值:**该方法不返回值。

**异常:**如果我们要复制的地图为空，该方法抛出*空指针异常*。

下面的程序说明了 java.util.WeakHashMap.putAll()方法的工作原理:
**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the putAll() method
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

        // Creating a new weakhash map and copying
        Map<Integer, String> new_weakhash_map = new 
                        WeakHashMap<Integer, String>();
        new_weakhash_map.putAll(weak_hash);

        // Displaying the final WeakHashMap
        System.out.println("The new map: " + 
                                    new_weakhash_map);
    }
}
```

**Output:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
The new map: {15=4, 30=You, 10=Geeks, 25=Welcomes, 20=Geeks}

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the putAll() method
import java.util.*;

public class WeakHash_Map_Demo {
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

        // Creating a new weakhash map and copying
        Map<String, Integer> new_weakhash_map = new 
                      WeakHashMap<String, Integer>();
        new_weakhash_map.putAll(weak_hash);

        // Displaying the final WeakHashMap
        System.out.println("The new map: " + 
                                   new_weakhash_map);
    }
}
```

**Output:**

```
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
The new map: {Welcomes=25, 4=15, You=30, Geeks=20}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。