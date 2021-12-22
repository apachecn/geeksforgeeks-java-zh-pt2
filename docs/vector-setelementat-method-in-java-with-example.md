# Java 中的 Vector setElementAt()方法，示例

> 原文:[https://www . geesforgeks . org/vector-setelementat-method-in-Java-with-example/](https://www.geeksforgeeks.org/vector-setelementat-method-in-java-with-example/)

**Java Vector** 的 **setElementAt()** 方法用于将该向量指定索引处的组件设置为指定对象。该位置的前一个组件将被丢弃。索引必须是大于或等于 0 且小于向量当前大小的值。

**语法:**

```java
public void setElementAt(E element, int index)

```

**参数:**该函数接受两个参数，如上语法所示，如下所述。

*   **元素**:是替换现有元素的新元素，与矢量属于同一对象类型。
*   **索引**:这是整型的，指的是向量中要替换的元素的位置。

**返回值:**这个方法不返回任何东西。

**异常:**如果索引超出范围(索引= size())，此方法将抛出**arrayindextofboundsexception**

下面的程序说明了 Java.util.Vector.setElementAt()方法:

**例 1:**

```java
// Java code to illustrate setElementAt()

import java.io.*;
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vector
            = new Vector<String>();

        // Use add() method to add elements in the vector
        vector.add("Geeks");
        vector.add("for");
        vector.add("Geeks");
        vector.add("10");
        vector.add("20");

        // Displaying the linkedvector
        System.out.println("Vector:"
                           + vector);

        // Using setElementAt() method to replace Geeks with GFG
        vector.setElementAt("GFG", 2);
        System.out.println("Geeks replaced with GFG");

        // Displaying the modified linkedvector
        System.out.println("The new Vector is:"
                           + vector);
    }
}
```

**Output:**

```java
Vector:[Geeks, for, Geeks, 10, 20]
Geeks replaced with GFG
The new Vector is:[Geeks, for, GFG, 10, 20]

```

**示例 2:** 演示 ArrayIndexOutOfBoundsException

```java
// Java code to illustrate setElementAt()

import java.io.*;
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vector
            = new Vector<String>();

        // Use add() method to add elements in the vector
        vector.add("Geeks");
        vector.add("for");
        vector.add("Geeks");
        vector.add("10");
        vector.add("20");

        // Displaying the linkedvector
        System.out.println("Vector:"
                           + vector);

        // Using setElementAt() method to replace 10th with GFG
        // and the 10th element does not exist
        System.out.println("Trying to replace 10th "
                           + "element with GFG");

        try {
            vector.setElementAt("GFG", 10);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Vector:[Geeks, for, Geeks, 10, 20]
Trying to replace 10th element with GFG
java.lang.ArrayIndexOutOfBoundsException: 10 >= 5

```