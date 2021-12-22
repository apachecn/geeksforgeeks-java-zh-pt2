# Java 中的 SortedMap lastKey()方法

> 原文:[https://www . geesforgeks . org/sorted map-last key-method-in-Java/](https://www.geeksforgeeks.org/sortedmap-lastkey-method-in-java/)

Java 中 **SortedMap 接口的 lastKey()方法用于返回当前在此地图中的最后一个或最大的键。**

**语法** :

```java
K lastKey()

```

其中，K 是该集合维护的密钥类型。

**参数**:本功能不接受任何参数。

**返回值**:返回当前地图中最后一个或最大的键

**异常**:如果这张地图是空的，它会抛出 *NoSuchElementException* 。

下面的程序说明了上述方法:

**程序 1** :

```java
// A Java program to demonstrate
// working of SortedSet
import java.util.*;

public class Main {
    public static void main(String[] args)
    {
        // Create a TreeSet and inserting elements
        SortedMap<Integer, String> mp = new TreeMap<>();

        // Adding Element to SortedSet
        mp.put(1, "One");
        mp.put(2, "Two");
        mp.put(3, "Three");
        mp.put(4, "Four");
        mp.put(5, "Five");

        // Returning the last key from the map
        System.out.print("Last Key in the map is : "
                         + mp.lastKey());
    }
}
```

**输出:**

```java
Last Key in the map is : 5

```

**程序二** :

```java
// A Java program to demonstrate
// working of SortedSet
import java.util.*;

public class Main {
    public static void main(String[] args)
    {
        // Create a TreeSet and inserting elements
        SortedMap<String, String> mp = new TreeMap<>();

        // Adding Element to SortedSet
        mp.put("One", "Geeks");
        mp.put("Two", "For");
        mp.put("Three", "Geeks");
        mp.put("Four", "Code");
        mp.put("Five", "It");

        // Returning the last key from the map
        System.out.print("Last Key in the map is : "
                         + mp.lastKey());
    }
}
```

**输出:**

```java
Last Key in the map is : Two

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/sortedmap . html # LastKey()](https://docs.oracle.com/javase/10/docs/api/java/util/SortedMap.html#lastKey())