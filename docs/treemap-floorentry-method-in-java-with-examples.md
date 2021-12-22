# Java 中的 TreeMap floorEntry()方法，带示例

> 原文:[https://www . geesforgeks . org/tree map-floor entry-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-floorentry-method-in-java-with-examples/)

Java . util . treemap .floor entry()方法用于返回与小于或等于给定键的最大键相关联的键值映射，如果没有这样的键，则返回 null。

**语法:**

```java
tree_map.floorEntry(K key)
```

**参数:**该方法在映射时取一个参数键进行匹配。

**返回值:**该方法返回最大键小于或等于键的条目，如果没有这样的键，则返回空。

**异常:**

*   **ClassCastException :** 如果指定的键无法与地图中当前的键进行比较，则会引发此异常。
*   **NullPointRexception:**如果指定的键为空，并且此映射使用自然排序，或者其比较器不允许空键，则会引发此异常。

**例 1:** 有钥匙时

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// TreeMap floorEntry() method
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<Integer, String> treemap
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys 
        treemap.put(20, "Twenty");
        treemap.put(10, "Ten");
        treemap.put(13, "Thirteen");
        treemap.put(60, "Sixty");
        treemap.put(50, "Fifty");

        System.out.println("The greatest key-value less than 18 is : "
                           + treemap.floorEntry(18));
    }
}
```

**Output**

```java
The greatest key-value less than 18 is : 13=Thirteen

```

**例 2:** 当没有这样的键时

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// TreeMap floorEntry() method
import java.util.TreeMap;

public class GFG {
    public static void main(String args[])
    {

         // Creating an empty TreeMap
        TreeMap<Integer, String> treemap
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys 
        treemap.put(10, "Akash");
        treemap.put(20, "Pratik");
        treemap.put(30, "Vaibhav");
        treemap.put(40, "Sagar");
        treemap.put(50, "Abhishek");

        // Printing floor entry
        System.out.println("The greatest key-value less than 5 is : "
                           + treemap.floorEntry(5));
    }
}
```

**Output**

```java
The greatest key-value less than 5 is : null

```