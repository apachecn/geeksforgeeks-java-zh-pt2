# Java 中的向量 firstElement()方法

> 原文:[https://www . geesforgeks . org/vector-first element-method-in-Java/](https://www.geeksforgeeks.org/vector-firstelement-method-in-java/)

**T1。Java 中的 firstElement()** 方法用于检索或获取 Vector 的第一个元素。它返回向量第 0 个<sup>索引处的元素</sup>

**语法:**

```java
Vector.firstElement()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回向量中存在的**第一个元素**。

下面的程序说明了 Java.util.Vector.firstElement()方法:

**程序 1:**

```java
// Java code to illustrate firstElement()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("4");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Displaying the first element
        System.out.println("The first element is: "
                           + vec_tor.firstElement());
    }
}
```

**Output:**

```java
Vector: [Welcome, To, Geeks, 4, Geeks]
The first element is: Welcome

```

**程序 2:**

```java
// Java code to illustrate firstElement()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements into the Vector
        vec_tor.add(10);
        vec_tor.add(15);
        vec_tor.add(30);
        vec_tor.add(20);
        vec_tor.add(5);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Displaying the first element
        System.out.println("The first element is: "
                           + vec_tor.firstElement());
    }
}
```

**Output:**

```java
Vector: [10, 15, 30, 20, 5]
The first element is: 10

```