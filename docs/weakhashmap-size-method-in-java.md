# Java 中 WeakHashMap size()方法

> 原文:[https://www . geeksforgeeks . org/weakashmap-size-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-size-method-in-java/)

WeakHashMap 类的 java.util.WeakHashMap.size()方法用于获取映射的大小，该大小是指映射中键值对或映射的数量。

**语法:**

```
WeaK_Hash_Map.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回地图的大小，这也意味着地图中存在的键值对的数量。

下面的程序说明了 java.util.WeakHashMap.size()方法:

**程序 1** :

```
// Java code to illustrate the size() method
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

        // Displaying the size of the map
        System.out.println("The size of the map is " + 
                                    weak_hash.size());
    }
}
```

**输出:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
The size of the map is 5

```

**程序二:**

```
// Java code to illustrate the size() method
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

        // Displaying the size of the map
        System.out.println("The size of the map is " + 
                                     weak_hash.size());
    }
}
```

**输出:**

```
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
The size of the map is 4

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。