# Java 中的向量 insertElementAt()方法，示例

> 原文:[https://www . geesforgeks . org/vector-insertelementat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/vector-insertelementat-method-in-java-with-examples/)

[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中[向量类](https://www.geeksforgeeks.org/java-util-vector-class-java/)的 *insertElementAt()方法用于在向量的指定索引处插入特定元素。元素和位置都作为参数传递。如果在指定的索引处插入一个元素，那么所有的元素都会被向上推一个，从而增加容量，为新元素创造空间。*

**语法:**

```
Vector.insertElementAt()
```

**参数:**该方法接受两个参数:

*   **元素:**需要插入到载体中。
*   **索引:**是指新元素要插入的位置(整型)

**抛出异常:**[arrayindexoofboundsexception](https://www.geeksforgeeks.org/array-index-out-of-bounds-exception-in-java/)如果索引是无效数字。

现在，让我们通过为字符串元素和整数元素提供示例来添加元素，并将我们的方法应用于这两个元素，只是为了熟悉这种方法在不同原始数据类型中的工作方式。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate insertElementAt() 
// Method of Vector class by 
// Adding String elements into the Vector

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty vector of string type
        Vector<String> vec_tor = new Vector<String>();

        // Adding custom elements into the vector
        // using add() method
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("4");
        vec_tor.add("Geeks");

        // Printing elements of vector
        System.out.println("Vector: " + vec_tor);

        // Inseting element at 3rd position
        // Custom specified
        vec_tor.insertElementAt("Hello", 2);

        // Inseting element at last position
        vec_tor.insertElementAt("World", 6);

        // Printing elements of final vector
        System.out.println("The final vector is "
                           + vec_tor);
    }
}
```

**Output:** 

```
Vector: [Welcome, To, Geeks, 4, Geeks]
The final vector is [Welcome, To, Hello, Geeks, 4, Geeks, World]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate insertElementAt()
// Method of Vector class by
// Adding Integer Elements into the Vector 

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty Vector of integer type
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Adding elements into the vector
        // using add() method
        vec_tor.add(10);
        vec_tor.add(20);
        vec_tor.add(30);
        vec_tor.add(40);
        vec_tor.add(50);

        // Printing the current elements of vector
        System.out.println("Vector: " + vec_tor);

        // Inseting element at 1st position
        vec_tor.insertElementAt(100, 0);

        // Inseting element at 5th position
        vec_tor.insertElementAt(200, 4);

        // Printing the final elements of Vector
        System.out.println("The final vector is "
                           + vec_tor);
    }
}
```

**Output:** 

```
Vector: [10, 20, 30, 40, 50]
The final vector is [100, 10, 20, 30, 200, 40, 50]
```