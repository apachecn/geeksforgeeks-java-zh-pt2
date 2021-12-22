# Java 中的 WeakHashMap isEmpty()方法，带示例

> 原文:[https://www . geeksforgeeks . org/weakashmap-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weakhashmap-isempty-method-in-java-with-examples/)

[HashMap 类](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)的 java.util.WeakHashMap.isEmpty()方法用于检查地图的空性。如果映射中没有键值对或映射，则该方法返回真，否则返回假。

**语法:**

```java
Weak_Hash_Map.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果映射为空或者不包含任何映射对，则该方法返回布尔值 true，否则返回布尔值 false。

下面的程序说明了 java.util.WeakHashMap.isEmpty()方法的工作原理:
**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the isEmpty() method
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
        System.out.println("The Mappings are: "+
                                      weak_hash);

        // Checking for the emptiness of Map
        System.out.println("Is the map empty? "+
                           weak_hash.isEmpty());
    }
}
```

**Output:**

```java
The Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
Is the map empty? false

```

**程序 2:** 为空的天气图

```java
// Java code to illustrate the isEmpty() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<String, Integer> weak_hash = new 
                  WeakHashMap<String, Integer>();

        // Displaying the WeakHashMap
        System.out.println("The Mappings are: "+
                                      weak_hash);

        // Checking for the emptiness of Map
        System.out.println("Is the map empty? "+
                            weak_hash.isEmpty());
    }
}
```

**Output:**

```java
The Mappings are: {}
Is the map empty? true

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

[Java.util.WeakHashmap 类](https://www.geeksforgeeks.org/java-util-weakhashmap-class-java/)的所有方法