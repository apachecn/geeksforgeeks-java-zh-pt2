# Java 中的向量容量()方法

> 原文:[https://www . geesforgeks . org/vector-capacity-method-in-Java/](https://www.geeksforgeeks.org/vector-capacity-method-in-java/)

Java 中的**Java . util . Vector . capacity()**方法用于获取 Vector 的容量或 Vector 中存在的数组的长度。

**语法:**

```java
Vector.capacity()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回向量中的容量或内部数据数组的长度，这是一个整数值。

下面的程序说明了 Java.util.Vector.capacity()方法:

**程序 1:** 带字符串元素的向量。

```java
// Java code to illustrate capacity()
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

        // Displaying the capacity of Vector
        System.out.println("The capacity is: " + vec_tor.capacity());
    }
}
```

**Output:**

```java
Vector: [Welcome, To, Geeks, 4, Geeks]
The capacity is: 10

```

**程序 2:** 带有整数元素的向量。

```java
// Java code to illustrate capacity()
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

        // Displaying the capacity of Vector
        System.out.println("The capacity is: " + vec_tor.capacity());
    }
}
```

**Output:**

```java
Vector: [10, 15, 30, 20, 5]
The capacity is: 10

```