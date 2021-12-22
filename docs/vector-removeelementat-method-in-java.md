# Java 中的 Vector removeElementAt()方法

> 原文:[https://www . geesforgeks . org/vector-removeelementat-method-in-Java/](https://www.geeksforgeeks.org/vector-removeelementat-method-in-java/)

**T1。removeElementAt(int index)** 方法用于从向量的特定位置或索引中移除元素。在这个过程中，在被移除的元素向下移动一个位置之后，向量的大小自动减少一个，所有其他元素也自动减少。

**语法:**

```java
Vector.removeElementAt(int index)
```

**参数:**该方法接受整数数据类型的强制参数**索引**，指定要从矢量中移除的元素的位置。

**返回值:**此法有**空**返回类型。这意味着它不返回任何东西。

下面的程序说明了 Java . util . vector . remove(int index)方法:

```java
// Java code to illustrate removeElementAt()
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

        // Output the Vector
        System.out.println("Vector: " + vec_tor);

        // Initial size
        System.out.println("The initial size is: " + vec_tor.size());

        // Remove the element at 3rd position
        vec_tor.removeElementAt(2);

        // Print the final Vector
        System.out.println("Final Vector: " + vec_tor);

        // Final size
        System.out.println("The final size is: " + vec_tor.size());
    }
}
```

**Output:**

```java
Vector: [Geeks, for, Geeks, 10, 20]
The initial size is: 5
Final Vector: [Geeks, for, 10, 20]
The final size is: 4

```