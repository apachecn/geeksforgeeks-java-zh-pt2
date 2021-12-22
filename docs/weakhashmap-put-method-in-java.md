# Java 中的 WeakHashMap put()方法

> 原文:[https://www . geeksforgeeks . org/weakashmap-put-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-put-method-in-java/)

WeakHashMap 的 Java . util . Weakashmap . put()方法用于将映射插入到地图中。这意味着我们可以将特定的键及其映射的值插入到特定的映射中。如果传递了一个现有的键，那么前一个值将被新值替换。如果传递了一个新的对，那么该对将作为一个整体被插入。

**语法:**

```java
Weak_Hash_Map.put(*key, value*)
```

**参数:**该方法采用两个参数，都是天气地图的对象类型。

*   *关键:*这是指需要插入到 Map 中进行映射的关键元素。
*   *值:*这是指上述键将映射到的值。

**返回值:**如果传递了一个现有的键，则返回前一个值。如果传递了新的对，则返回空值。

下面的程序是用来说明 java.util.WeakHashMap.put()方法:
**程序 1:** 在传递一个已有密钥时的工作方式。

```java
// Java code to illustrate the put() method
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

        // Inserting existing key along with new value
        String returned_value = 
                     (String)weak_hash.put(20, "All");

        // Verifying the returned value
        System.out.println("Returned value is: " + 
                                   returned_value);

        // Displayin the new map
        System.out.println("New map is: " + weak_hash);
    }
}
```

**Output:**

```java
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
Returned value is: Geeks
New map is: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=All}

```

**程序 2:** 传递新密钥时。

```java
// Java code to illustrate the put() method
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

        // Inserting existing key along with new value
        String returned_value = 
                      (String)weak_hash.put(50, "All");

        // Verifying the returned value
        System.out.println("Returned value is: " + 
                                      returned_value);

        // Displayin the new map
        System.out.println("New map is: " + weak_hash);
    }
}
```

**Output:**

```java
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
Returned value is: null
New map is: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks, 50=All}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。