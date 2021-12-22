# Java 中的向量 hashCode()方法

> 原文:[https://www . geesforgeks . org/vector-hashcode-method-in-Java/](https://www.geeksforgeeks.org/vector-hashcode-method-in-java/)

**T1。用 Java 中的 hashCode()** 方法得到这个向量的 hashCode 值。

**语法:**

```java
Vector.hashCode()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回整数类型的该向量的**哈希码值**。

下面的程序说明了 Java.util.Vector.hashCode()方法:

**程序 1:** 带字符串元素的向量。

```java
// Java code to illustrate hashCode()
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

        // Displaying the hashCode value of Vector
        System.out.println("The hashCode value is: "
                           + vec_tor.hashCode());
    }
}
```

**Output:**

```java
Vector: [Welcome, To, Geeks, 4, Geeks]
The hashCode value is: -878886256

```

**程序 2:** 带有整数元素的向量。

```java
// Java code to illustrate hashCode()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements into the Vector
        vec_tor.add(10);
        vec_tor.add(20);
        vec_tor.add(30);
        vec_tor.add(40);
        vec_tor.add(50);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Displaying the hashCode value of Vector
        System.out.println("The hashCode value is: "
                           + vec_tor.hashCode());
    }
}
```

**Output:**

```java
Vector: [10, 20, 30, 40, 50]
The hashCode value is: 38490301

```