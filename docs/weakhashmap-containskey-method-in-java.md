# Java 中的 WeakHashMap containsKey()方法

> 原文:[https://www . geesforgeks . org/weakashmap-contains key-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-containskey-method-in-java/)

Java . util . WeakHashMap . contains KeY()方法用于检查特定的键是否被映射到 Weakashmap 中。它将关键元素作为参数，如果该元素在映射中被映射，则返回 True。

**语法:**

```
Weak_Hash_Map.containsKey(*key_element*)
```

**参数:**该方法只取一个参数 *key_element* ，该参数是指映射应该在地图内部检查的键。

**返回值:**如果检测到键的存在，则该方法返回布尔值 true，否则返回 false。

下面的程序用来说明 Java . util . weakashmap . contains key()方法:
**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the containsKey() method
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

        // Checking for the key_element '20'
        System.out.println("Is the key '20' present? " + 
                                  weak_hash.containsKey(20));

        // Checking for the key_element '5'
        System.out.println("Is the key '5' present? " + 
                                   weak_hash.containsKey(5));
    }
}
```

**Output:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
Is the key '20' present? true
Is the key '5' present? false

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the containsKey() method
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

        // Checking for the key_element 'Welcomes'
        System.out.println("Is the key 'Welcomes' present? " + 
                                  weak_hash.containsKey("Welcomes"));

        // Checking for the key_element 'World'
        System.out.println("Is the key 'World' present? " + 
                                      weak_hash.containsKey("World"));
    }
}
```

**Output:**

```
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
Is the key 'Welcomes' present? true
Is the key 'World' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。