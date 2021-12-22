# Java 中的 Vector removeRange()方法，示例

> 原文:[https://www . geesforgeks . org/vector-remove range-method-in-Java-with-example/](https://www.geeksforgeeks.org/vector-removerange-method-in-java-with-example/)

Java 中 **Vector** 的 **removeRange()** 方法用于从 Vector 对象中移除指定范围内的所有元素。它将任何后续元素向左移动。这个调用通过(toIndex-fromIndex)元素来缩短向量，其中 toIndex 是结束索引，fromIndex 是开始索引，其中所有元素都将被删除。(如果 toIndex==fromIndex，此操作无效)

**语法:**

```java
removeRange(int fromIndex, int toIndex)
```

**参数:**有两个参数:

*   **From index:** The starting index from which to delete the index element.
*   **to index:** Within the range of [from index to index], all elements have been removed.

**返回值:**此方法不返回值。它只移除指定范围内的所有元素。

**异常:**如果 fromIndex 或 toIndex 超出范围(fromIndex = size()或 toIndex > size()或 toIndex < fromIndex)，此方法将抛出***indexout of bound 异常***

**例 1**:

```java
// Java program to understand
// about vector.removeRange() function

mport java.util.*;

// sice vector removeRange() method is protected
// Therefore Vector is inherited
public class GFG extends Vector<String> {

    // main method
    public static void main(String[] args)
    {
        // creating GFG object
        GFG v = new GFG();

        // inserting elements into the vector
        v.add("Geeks");
        v.add("for");
        v.add("Geeks");
        v.add("Ankit");
        v.add("Mishra");
        v.add("MNNIT");

        // printing vector before deleting
        System.out.println("Vector before calling"
                           + " removeRange(): " + v);

        // calling removeRange() function

        v.removeRange(1, 3);
        // printing after removeRange() called

        System.out.println("Vector after calling"
                           + " removeRange(1, 3): " + v);
    }
}
```

//sice vector removeRange()方法受保护//因此 Vector 是继承的**输出:**

```java
Vector before calling removeRange(): [Geeks, for, Geeks, Ankit, Mishra, MNNIT]
Vector after calling removeRange(1, 3): [Geeks, Ankit, Mishra, MNNIT]

```

**例 2** :

```java
// Java program to understand
// about vector.removeRange() function

import java.util.*;

// sice vector removeRange() method is protected
// Therefore Vector is inherited
public class GFG extends Vector<String> {

    // main method
    public static void main(String[] args)
    {
        // creating GFG object
        GFG v = new GFG();

        // inserting elements into the vector
        v.add("Geeks");
        v.add("for");
        v.add("Geeks");
        v.add("Ankit");
        v.add("Mishra");
        v.add("MNNIT");

        // printing vector before deleting
        System.out.println("Vector before calling "
                           + "removeRange(): "
                           + v);

        // calling removeRange() function

        try {
            // It will generate Runtime Error
            v.removeRange(1, 16);
            // printing after removeRange() called

            System.out.println("Vector after "
                               + "calling removeRange(1, 3): "
                               + v);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Vector before calling removeRange(): [Geeks, for, Geeks, Ankit, Mishra, MNNIT]
java.lang.ArrayIndexOutOfBoundsException

```

**注意:**强烈建议如果我们想在任何类中调用 removeRange()方法，那么该类必须直接或间接扩展 Vector 类，否则我们将得到编译错误:**方法 removeRange()具有受保护的访问权限。**