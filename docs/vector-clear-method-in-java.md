# Java 中的向量清零()方法

> 原文:[https://www.geeksforgeeks.org/vector-clear-method-in-java/](https://www.geeksforgeeks.org/vector-clear-method-in-java/)

方法用于从向量中移除所有元素。使用 clear()方法只会清除向量中的所有元素，而不会删除向量。换句话说，我们可以说 clear()方法仅用于清空现有向量。

**语法:**

```java
Vector.clear()
```

**参数:**该方法不取任何参数

**返回值:**函数不返回值。

下面的程序说明了 Java.util.Vector.clear()方法。

**例 1:**

```java
// Java code to illustrate clear()
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vt = new Vector<String>();

        // Use add() method to add elements into the Vector
        vt.add("Welcome");
        vt.add("To");
        vt.add("Geeks");
        vt.add("4");
        vt.add("Geeks");

        // Displaying the Vector
        System.out.println("Vector: " + vt);

        // Clearing the Vector using clear() method
        vt.clear();

        // Displaying the final vector after clearing;
        System.out.println("The final Vector: " + vt);
    }
}
```

**Output:**

```java
Vector: [Welcome, To, Geeks, 4, Geeks]
The final Vector: []

```

**例 2:**

```java
// Java code to illustrate clear()
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vt = new Vector<Integer>();

        // Use add() method to add elements into the Queue
        vt.add(10);
        vt.add(15);
        vt.add(30);
        vt.add(20);
        vt.add(5);

        // Displaying the Vector
        System.out.println("Vector: " + vt);

        // Clearing the Vector using clear() method
        vt.clear();

        // Displaying the final vector after clearing;
        System.out.println("The final Vector: " + vt);
    }
}
```

**Output:**

```java
Vector: [10, 15, 30, 20, 5]
The final Vector: []

```