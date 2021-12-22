# Java 中的 SortedMap firstKey()方法

> 原文:[https://www . geesforgeks . org/sorted map-first key-method-in-Java/](https://www.geeksforgeeks.org/sortedmap-firstkey-method-in-java/)

Java 中 **SortedMap 接口的 firstKey()方法**用来返回当前在这个映射中的第一个或者最低的键。

**语法** :

```java
K firstKey()

```

其中，K 是该集合维护的密钥类型。

**参数**:本功能不接受任何参数。

**返回值**:返回当前地图中第一个打印的最低键

**异常**:如果这张地图是空的，它会抛出 *NoSuchElementException* 。

下面的程序说明了上述方法:

**程序 1** :

```java
// A Java program to demonstrate
// working of SortedMap
import java.util.*;

public class Main {
    public static void main(String[] args)
    {
        // Create a TreeMap of SortedMap
        SortedMap<Integer, String> mp = new TreeMap<>();

        // Adding Element to SortedSet
        mp.put(1, "One");
        mp.put(5, "Five");
        mp.put(2, "Two");
        mp.put(3, "Three");
        mp.put(9, "Nine");

        // Returning the first key element
        // from the map
        System.out.print("First Key in the map : "
                         + mp.firstKey());
    }
}
```

**输出:**

```java
First Key in the map : 1

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

        // Returning the first key
        // from the map
        System.out.print("First Key in the map is : "
                         + mp.firstKey());
    }
}
```

**输出:**

```java
First Key in the map is : Five

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/sortedmap . html # first key()](https://docs.oracle.com/javase/10/docs/api/java/util/SortedMap.html#firstKey())