# Java 中的向量迭代器()方法，示例

> 原文:[https://www . geesforgeks . org/vector-iterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/vector-iterator-method-in-java-with-examples/)

[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中的[向量类](https://www.geeksforgeeks.org/java-util-vector-class-java/)的*迭代器()方法用于返回与向量元素相同的迭代器。元素从向量中随机返回。*

**语法:**

```
Iterator *iterate_value* = Vector.iterator();
```

**参数:**函数不取任何参数。

**返回类型:**该方法迭代向量的元素并返回值(迭代器)。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate iterator() Method
// of Vector class

// Importing required classes
import java.util.*;
import java.util.Vector;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty Vector of string type
        Vector<String> vector = new Vector<String>();

        // Adding elements into the Vector
        // using add() method
        vector.add("Welcome");
        vector.add("To");
        vector.add("Geeks");
        vector.add("4");
        vector.add("Geeks");

        // Printing and displaying the Vector
        System.out.println("Vector: " + vector);

        // Now creating an iterator
        Iterator value = vector.iterator();

        // Display message only
        System.out.println("The iterator values are: ");

        // Condition holds true till there is single element
        // remaining using hasNext() method
        while (value.hasNext()) {

            // Displaying the values
            // after iterating through the vector
            System.out.println(value.next());
        }
    }
}
```

**Output:** 

```
Vector: [Welcome, To, Geeks, 4, Geeks]
The iterator values are: 
Welcome
To
Geeks
4
Geeks
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate iterator() method usage
// with usage of hashCode() method

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty Vector of integer type
        Vector<Integer> vector = new Vector<Integer>();

        // Adding custom elements into the Vector
        // using add() method
        vector.add(10);
        vector.add(20);
        vector.add(30);
        vector.add(40);
        vector.add(50);

        // Displaying the Vector
        System.out.println("Vector: " + vector);

        // Creating an iterator
        Iterator value = vector.iterator();

        // Display message for better readability
        System.out.println("The iterator values are: ");

        // Holds true till there is single element
        while (value.hasNext()) {

            // Printing the values after iterating
            // through the vector
            // using next() method
            System.out.println(value.next());
        }
    }
}
```

**Output:** 

```
Vector: [10, 20, 30, 40, 50]
The iterator values are: 
10
20
30
40
50
```