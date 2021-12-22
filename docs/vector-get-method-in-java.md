# Java 中的 Vector get()方法

> 原文:[https://www.geeksforgeeks.org/vector-get-method-in-java/](https://www.geeksforgeeks.org/vector-get-method-in-java/)

**java.util.vector.get()** 方法用于从 vector 中获取或检索特定索引处的元素。

**语法:**

```
Vector.get(int index)
```

**参数:**该方法接受一个强制参数*索引*，该参数为整数数据类型。它指定要从向量中提取的元素的位置或索引。

**返回值:**该方法返回出现在参数索引指定位置的*元素*。

下面的程序说明了 Java.util.Vector.get()方法:

**程序 1** :

```
// Java code to illustrate get() method
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

        // Fetching the specific element from the Vector
        System.out.println("The element is: "
                           + vec_tor.get(2));
    }
}
```

**Output:**

```
Vector: [Geeks, for, Geeks, 10, 20]
The element is: Geeks

```

**程序 2** :

```
// Java code to illustrate get() method
import java.util.Vector;

public class VectorDemo {
    public static void main(String args[])
    {

        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements in the Vector
        vec_tor.add("1");
        vec_tor.add("2");
        vec_tor.add("3");
        vec_tor.add("10");
        vec_tor.add("20");

        // Displaying the Vector
        System.out.println("Vector: "
                           + vec_tor);

        // Fetching the specific element from the Vector
        System.out.println("The element is: "
                           + vec_tor.get(4));
    }
}
```

**Output:**

```
Vector: [1, 2, 3, 10, 20]
The element is: 20

```