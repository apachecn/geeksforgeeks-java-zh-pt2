# Java 中的向量保证能力()方法，示例

> 原文:[https://www . geesforgeks . org/vector-ensurecapacity-method-in-Java-with-example/](https://www.geeksforgeeks.org/vector-ensurecapacity-method-in-java-with-example/)

**Java.util.Vector** 类的 **ensureCapacity()** 方法增加了这个 Vector 实例的容量(如果需要的话)，以确保它至少可以容纳最小容量参数指定的元素数量。

**语法:**

```
public void ensureCapacity(int minCapacity)
```

**参数:**该方法以**期望最小容量**为参数。

以下是说明**保证能力()**方法的例子。

**例 1:**

```
// Java program to demonstrate
// ensureCapacity() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of Vector<Integer>
            Vector<Integer>
                vector = new Vector<Integer>();

            // adding element to vector
            vector.add(10);
            vector.add(20);
            vector.add(30);
            vector.add(40);

            // Print the Vector
            System.out.println("Vector: "
                               + vector);

            // ensure that the Vector
            // can hold upto 5000 elements
            // using ensureCapacity() method
            vector.ensureCapacity(5000);

            // Print
            System.out.println("Vector can now"
                               + " surely store upto"
                               + " 5000 elements.");
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Vector: [10, 20, 30, 40]
Vector can now surely store upto 5000 elements.

```

**例 2:**

```
// Java program to demonstrate
// ensureCapacity() method for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of Vector<Integer>
            Vector<String>
                vector = new Vector<String>();

            // adding element to vector
            vector.add("A");
            vector.add("B");
            vector.add("C");
            vector.add("D");

            // Print the Vector
            System.out.println("Vector: "
                               + vector);

            // ensure that the Vector
            // can hold upto 400 elements
            // using ensureCapacity() method
            vector.ensureCapacity(400);

            // Print
            System.out.println("Vector can now"
                               + " surely store upto"
                               + " 400 elements.");
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Vector: [A, B, C, D]
Vector can now surely store upto 400 elements.

```