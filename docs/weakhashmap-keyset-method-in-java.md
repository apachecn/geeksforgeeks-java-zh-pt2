# Java 中的 WeakHashMap keySet()方法

> 原文:[https://www . geeksforgeeks . org/weakashmap-key set-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-keyset-method-in-java/)

java 中的 java.util.WeakHashMap.keySet()方法用于创建一组包含在哈希映射中的关键元素。它基本上返回一个键的集合视图，或者我们可以创建一个新的集合并将键元素存储在其中。

**语法:**

```
Weak_Hash_Map.keySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个具有弱哈希映射关键字的集合。

下面的程序用来说明 java.util.WeakHashMap.keySet()的工作方法:
**程序 1:** 将字符串值映射到整键。

```
// Java code to illustrate the keySet() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<Integer, String> weak_hash = 
                  new WeakHashMap<Integer, String>();

        // Mapping string values to int keys
        weak_hash.put(10, "Geeks");
        weak_hash.put(15, "4");
        weak_hash.put(20, "Geeks");
        weak_hash.put(25, "Welcomes");
        weak_hash.put(30, "You");

        // Displaying the WeakHashMap
        System.out.println("Initial Mappings are: " +
                                          weak_hash);

        // Using keySet() to get the set view of keys
        System.out.println("The set is: " + 
                                  weak_hash.keySet());
    }
}
```

**Output:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
The set is: [30, 15, 10, 25, 20]

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the keySet() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<String, Integer> weak_hash = 
                    new WeakHashMap<String, Integer>();

        // Mapping int values to string keys
        weak_hash.put("Geeks", 10);
        weak_hash.put("4", 15);
        weak_hash.put("Geeks", 20);
        weak_hash.put("Welcomes", 25);
        weak_hash.put("You", 30);

        // Displaying the WeakHashMap
        System.out.println("Initial Mappings are: " + 
                                           weak_hash);

        // Using keySet() to get the set view of keys
        System.out.println("The set is: " + 
                                  weak_hash.keySet());
    }
}
```

**Output:**

```
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
The set is: [Welcomes, 4, You, Geeks]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。