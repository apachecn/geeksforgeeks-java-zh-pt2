# Java 中的矢量元素 At()方法

> 原文:[https://www . geesforgeks . org/vector-element at-method-in-Java/](https://www.geeksforgeeks.org/vector-elementat-method-in-java/)

**T1。方法用于从向量中获取或检索特定索引处的元素。**

**语法:**

```
Vector.elementAt(int pos)
```

**参数:**该方法接受整数数据类型的强制参数*位置*，该参数指定要从向量中提取的元素的位置或索引。

**返回值:**该方法返回出现在参数*位置*指定位置的*元素*。

下面的程序说明了 Java.util.Vector.get()方法:

**程序 1:**

```
// Java code to illustrate elementAt() method
import java.util.Vector;

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
        System.out.println("Vector: "
                           + vec_tor);

        // Fetching the specific element from the Vector
        System.out.println("The element is: "
                           + vec_tor.elementAt(3));
    }
}
```

**Output:**

```
Vector: [Geeks, for, Geeks, 10, 20]
The element is: 10

```

**程序 2:**

```
// Java code to illustrate elementAt() method
import java.util.Vector;

public class VectorDemo {
    public static void main(String args[])
    {

        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements in the Vector
        vec_tor.add(1);
        vec_tor.add(2);
        vec_tor.add(3);
        vec_tor.add(4);
        vec_tor.add(5);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Fetching the specific element from the Vector
        System.out.println("The element is: "
                           + vec_tor.elementAt(1));
    }
}
```

**Output:**

```
Vector: [1, 2, 3, 4, 5]
The element is: 2

```