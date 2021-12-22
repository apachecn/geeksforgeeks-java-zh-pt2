# Java 中的 Vector trimToSize()方法，示例

> 原文:[https://www . geeksforgeeks . org/vector-trimtosize-method-in-Java-with-example/](https://www.geeksforgeeks.org/vector-trimtosize-method-in-java-with-example/)

Java 中[](https://www.geeksforgeeks.org/arrayVector-in-java/)**的 **trimToSize()** 方法将向量实例的容量修剪为向量的当前大小。此方法用于将矢量实例修剪到其包含的元素数量。**

****语法:****

```
trimToSize()
```

****参数:**不接受任何参数。**

****返回值:**不返回值。它将此矢量实例的容量修剪为它包含的元素数量。**

**下面的程序说明了 trimTosize()方法:**

****例 1:****

```
// Java code to demonstrate the working of
// trimTosize() method in Vector

import java.util.Vector;

public class GFG {
    public static void main(String[] args)
    {

        // creating an Empty Integer Vector
        Vector<Integer> vector
            = new Vector<Integer>(9);

        // using add(), add 5 values
        vector.add(2);
        vector.add(4);
        vector.add(5);
        vector.add(6);
        vector.add(11);

        // Displaying the Vector
        System.out.println("Initial Vector is: " + vector);

        // Displaying the Vector
        System.out.println("Initial size is: " + vector.size());

        // trims the size to the number of elements
        vector.trimToSize();

        // Displaying the Vector
        System.out.println("Size after using trimToSize(): "
                           + vector.size());
    }
}
```

****Output:**

```
Initial Vector is: [2, 4, 5, 6, 11]
Initial size is: 5
Size after using trimToSize(): 5

```** 

****例 2:****

```
// Java code to demonstrate the working of
// trimTosize() method in Vector

import java.util.Vector;

public class GFG {
    public static void main(String[] args)
    {

        // creating vector type object
        Vector<String> vector = new Vector<String>();

        // Inserting elements into the table
        vector.add("Geeks");
        vector.add("4");
        vector.add("Geeks");
        vector.add("Welcomes");
        vector.add("You");

        // Displaying the Vector
        System.out.println("Initial Vector is: " + vector);

        // Displaying the Vector
        System.out.println("Initial size is: " + vector.size());

        // trims the size to the number of elements
        vector.trimToSize();

        // Displaying the Vector
        System.out.println("Size after using trimToSize(): "
                           + vector.size());
    }
}
```

****Output:**

```
Initial Vector is: [Geeks, 4, Geeks, Welcomes, You]
Initial size is: 5
Size after using trimToSize(): 5

```**