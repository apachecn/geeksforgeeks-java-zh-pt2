# Java 中的向量集()方法

> 原文:[https://www.geeksforgeeks.org/vector-set-method-in-java/](https://www.geeksforgeeks.org/vector-set-method-in-java/)

**T1。set()** 方法用于用另一个元素替换使用 vector 类创建的向量中的任何特定元素。

**语法:**

```
Vector.set(int index, Object element)
```

**参数:**该函数接受两个强制参数，如上语法所示，如下所述。

*   **索引**:这是整型的，指的是向量中要替换的元素的位置。
*   **元素**:是替换现有元素的新元素，与矢量属于同一对象类型。

**返回值:**该方法返回向量中被新值替换的前一个值。

下面的程序说明了 Java.util.Vector.set()方法:

**程序 1:**

```
// Java code to illustrate set()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements in the vector
        vec_tor.add("Geeks");
        vec_tor.add("for");
        vec_tor.add("Geeks");
        vec_tor.add("10");
        vec_tor.add("20");

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Using set() method to replace Geeks with GFG
        System.out.println("The Object that is replaced is: "
                           + vec_tor.set(2, "GFG"));

        // Using set() method to replace 20 with 50
        System.out.println("The Object that is replaced is: "
                           + vec_tor.set(4, "50"));

        // Displaying the modified vector
        System.out.println("The new Vector is:" + vec_tor);
    }
}
```

**Output:**

```
Vector: [Geeks, for, Geeks, 10, 20]
The Object that is replaced is: Geeks
The Object that is replaced is: 20
The new Vector is:[Geeks, for, GFG, 10, 50]

```

**程序 2:**

```
// Java code to illustrate set()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements in the vector
        vec_tor.add(12);
        vec_tor.add(23);
        vec_tor.add(22);
        vec_tor.add(10);
        vec_tor.add(20);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Using set() method to replace 12 with 21
        System.out.println("The Object that is replaced is: "
                           + vec_tor.set(0, 21));

        // Using set() method to replace 20 with 50
        System.out.println("The Object that is replaced is: "
                           + vec_tor.set(4, 50));

        // Displaying the modified vector
        System.out.println("The new Vector is:" + vec_tor);
    }
}
```

**Output:**

```
Vector: [12, 23, 22, 10, 20]
The Object that is replaced is: 12
The Object that is replaced is: 20
The new Vector is:[21, 23, 22, 10, 50]

```