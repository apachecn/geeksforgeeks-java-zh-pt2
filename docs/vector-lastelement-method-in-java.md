# Java 中的 Vector lastElement()方法

> 原文:[https://www . geesforgeks . org/vector-last element-method-in-Java/](https://www.geeksforgeeks.org/vector-lastelement-method-in-java/)

**T1。Java 中的 lastElement()** 方法用于检索或获取 Vector 的最后一个元素。它返回出现在向量最后一个索引处的元素。

**语法:**

```
Vector.lastElement()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回矢量中最后一个元素**。**

**下面的程序说明了 Java.util.Vector.lastElement()方法:**

****程序 1:****

```
// Java code to illustrate lastElement()
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

        // Displaying the last element
        System.out.println("The last element is: "
                           + vec_tor.lastElement());
    }
}
```

****Output:**

```
Vector: [Welcome, To, Geeks, 4, Geeks]
The last element is: Geeks

```** 

****程序 2:****

```
// Java code to illustrate lastElement()
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

        // Displaying the last element
        System.out.println("The last element is: "
                           + vec_tor.lastElement());
    }
}
```

****Output:**

```
Vector: [10, 15, 30, 20, 5]
The last element is: 5

```**