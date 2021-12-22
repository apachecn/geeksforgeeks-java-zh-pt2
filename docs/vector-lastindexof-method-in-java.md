# Java 中的 Vector lastIndexOf()方法

> 原文:[https://www . geesforgeks . org/vector-last indexof-method-in-Java/](https://www.geeksforgeeks.org/vector-lastindexof-method-in-java/)

Java.util.Vector 。方法用于检查和查找向量中特定元素的出现。如果该元素存在于向量中，则 lastIndexOf()方法返回该元素最后一次出现的索引，否则返回-1。此方法用于查找向量中特定元素的最后一次出现。

**语法:**

```java
Vector.lastIndexOf(Object element)
```

**参数:**参数*元素*属于矢量类型。它指的是需要检查最后一次出现的元素。

**返回值:**该方法返回元素在向量中最后一次出现的位置。如果该元素不在向量中，则该方法返回-1。返回值是整数类型。

下面的程序说明了 Java.util.Vector.lastIndexOf()方法:

**程序 1:**

```java
// Java code to illustrate lastIndexOf()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {

        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements in the Vector
        vec_tor.add("Geeks");
        vec_tor.add("for");
        vec_tor.add("Geeks");
        vec_tor.add("10");
        vec_tor.add("20");

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // The last position of an element is returned
        System.out.println("Last occurrence of Geeks is at index: "
                           + vec_tor.lastIndexOf("Geeks"));
        System.out.println("Last occurrence of 10 is at index: "
                           + vec_tor.lastIndexOf("10"));
    }
}
```

**Output:**

```java
Vector: [Geeks, for, Geeks, 10, 20]
Last occurrence of Geeks is at index: 2
Last occurrence of 10 is at index: 3

```

**程序 2:**

```java
// Java code to illustrate lastIndexOf()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {

        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements in the Vector
        vec_tor.add(10);
        vec_tor.add(22);
        vec_tor.add(3);
        vec_tor.add(10);
        vec_tor.add(20);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // The last position of an element is returned
        System.out.println("Last occurrence of 10 is at index: "
                           + vec_tor.lastIndexOf(10));
        System.out.println("Last occurrence of 20 is at index: "
                           + vec_tor.lastIndexOf(20));
    }
}
```

**Output:**

```java
Vector: [10, 22, 3, 10, 20]
Last occurrence of 10 is at index: 3
Last occurrence of 20 is at index: 4

```