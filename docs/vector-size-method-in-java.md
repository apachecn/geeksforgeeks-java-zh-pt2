# Java 中的向量大小()方法

> 原文:[https://www.geeksforgeeks.org/vector-size-method-in-java/](https://www.geeksforgeeks.org/vector-size-method-in-java/)

**T1。Java 中的 size()** 方法用于获取 Vector 的大小或 Vector 中存在的元素数量。

**语法:**

```
Vector.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回矢量中存在的*大小或元素数量*。

下面的程序说明了 Java.util.Vector.size()方法:

**程序 1:** 带字符串元素的向量。

```
// Java code to illustrate size()
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

        // Displaying the size of Vector
        System.out.println("The size is: " + vec_tor.size());
    }
}
```

**Output:**

```
Vector: [Welcome, To, Geeks, 4, Geeks]
The size is: 5

```

**程序 2:** 带有整数元素的向量。

```
// Java code to illustrate size()
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

        // Displaying the size of Vector
        System.out.println("The size is: " + vec_tor.size());
    }
}
```

**Output:**

```
Vector: [10, 15, 30, 20, 5]
The size is: 5

```