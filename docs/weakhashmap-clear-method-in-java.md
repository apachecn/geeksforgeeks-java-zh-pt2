# Java 中的 WeakHashMap clear()方法

> 原文:[https://www . geeksforgeeks . org/weakashmap-clear-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-clear-method-in-java/)

java 中的 java.util.WeakHashMap.clear()方法用于清除和移除指定映射中的所有元素或映射。

**语法:**

```java
Weak_Hash_Map.clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

下面的程序用来说明 java.util.WeakHashMap.clear()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the clear() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<Integer, String> weak_hash = new WeakHashMap<Integer, String>();

        // Mapping string values to int keys
        weak_hash.put(10, "Geeks");
        weak_hash.put(15, "4");
        weak_hash.put(20, "Geeks");
        weak_hash.put(25, "Welcomes");
        weak_hash.put(30, "You");

        // Displaying the WeakHashMap
        System.out.println("Initial Mappings are: "
                           + weak_hash);

        // Clearing the map using clear()
        weak_hash.clear();

        // Displaying the final WeakHashMap
        System.out.println("Final Map: "
                           + weak_hash);
    }
}
```

**输出:**

```java
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
Final Map: {}

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the clear() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<String, Integer> weak_hash = new WeakHashMap<String, Integer>();

        // Mapping int values to string keys
        weak_hash.put("Geeks", 10);
        weak_hash.put("4", 15);
        weak_hash.put("Geeks", 20);
        weak_hash.put("Welcomes", 25);
        weak_hash.put("You", 30);

        // Displaying the WeakHashMap
        System.out.println("Initial Mappings are: " + weak_hash);

        // Clearing the map using clear()
        weak_hash.clear();

        // Displaying the final WeakHashMap
        System.out.println("Final Map: "
                           + weak_hash);
    }
}
```

**输出:**

```java
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
Final Map: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。