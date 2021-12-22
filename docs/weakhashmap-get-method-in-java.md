# Java 中的 WeakHashMap get()方法

> 原文:[https://www . geeksforgeeks . org/weakashmap-get-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-get-method-in-java/)

WeakHashMap 类的 java.util.WeakHashMap.get()方法用于检索或获取参数中提到的特定键映射的值。当映射不包含键的这种映射时，它返回空值。

**语法:**

```java
WeakHashMap.get(*Object key_element*)
```

**参数:**该方法取一个对象类型的参数 *key_element* ，指的是应该取关联值的键。

**返回值:**该方法返回与参数中*键 _ 元素*相关联的值。

下面的程序说明了 java.util.WeakHashMap.get()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate the get() method
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
        System.out.println("Initial Mappings are: " + weak_hash);

        // Getting the value of 25
        System.out.println("The Value is: " + weak_hash.get(25));

        // Getting the value of 10
        System.out.println("The Value is: " + weak_hash.get(10));
    }
}
```

**输出:**

```java
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
The Value is: Welcomes
The Value is: Geeks

```

**程序二:**

```java
// Java code to illustrate the get() method
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

        // Getting the value of "Geeks"
        System.out.println("The Value is: " + weak_hash.get("Geeks"));

        // Getting the value of "You"
        System.out.println("The Value is: " + weak_hash.get("You"));
    }
}
```

**输出:**

```java
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
The Value is: 20
The Value is: 30

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。