# Java 中的 Vector equals()方法

> 原文:[https://www.geeksforgeeks.org/vector-equals-method-in-java/](https://www.geeksforgeeks.org/vector-equals-method-in-java/)

**T1。Java 中 Vector 类的 equals(Object obj)** 方法用于验证一个对象与一个向量的相等性并进行比较。只有当两个向量包含相同顺序的相同元素时，列表才返回 true。

**语法:**

```
first_vector.equals(second_vector)
```

**参数:**该方法接受一个强制参数 **second_vector** ，它指的是要与第一个 vector 进行比较的第二个 Vector。

**返回值:**该方法返回**真**如果等式成立，并且对象和向量相等，则返回**假**。

下面的程序用来说明 java.util.Vector.elements()方法的工作原理:

**程序 1:**

```
// Java code to illustrate the equals() method
import java.util.*;

public class Vector_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Vector
        Vector<String> vec_tor1 = new Vector<String>(5);

        // Inserting elements into the table
        vec_tor1.add("Geeks");
        vec_tor1.add("4");
        vec_tor1.add("Geeks");
        vec_tor1.add("Welcomes");
        vec_tor1.add("You");

        // Displaying the Vector
        System.out.println("The Vector is: "
                           + vec_tor1);

        // Creating an empty Vector
        Vector<String> vec_tor2 = new Vector<String>(5);

        // Inserting elements into the table
        vec_tor2.add("Geeks");
        vec_tor2.add("4");
        vec_tor2.add("Geeks");
        vec_tor2.add("Welcomes");
        vec_tor2.add("You");

        // Displaying the Vector
        System.out.println("The Vector is: "
                           + vec_tor2);

        System.out.println("Are both of them equal? "
                           + vec_tor1.equals(vec_tor2));
    }
}
```

**Output:**

```
The Vector is: [Geeks, 4, Geeks, Welcomes, You]
The Vector is: [Geeks, 4, Geeks, Welcomes, You]
Are both of them equal? true

```

**程序 2 :**

```
// Java code to illustrate the equals() method
import java.util.*;

public class Vector_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Vector
        Vector<Integer> vec_tor1 = new Vector<Integer>(5);

        // Inserting elements into the table
        vec_tor1.add(10);
        vec_tor1.add(15);
        vec_tor1.add(20);
        vec_tor1.add(25);
        vec_tor1.add(30);

        // Displaying the Vector
        System.out.println("The Vector is: " + vec_tor1);

        // Creating an empty Vector
        Vector<Integer> vec_tor2 = new Vector<Integer>(6);

        // Inserting elements into the table
        vec_tor2.add(10);
        vec_tor2.add(15);
        vec_tor2.add(20);
        vec_tor2.add(25);
        vec_tor2.add(30);
        vec_tor2.add(40);

        // Displaying the Vector
        System.out.println("The Vector is: " + vec_tor2);

        System.out.println("Are both of them equal? "
                           + vec_tor1.equals(vec_tor2));
    }
}
```

**Output:**

```
The Vector is: [10, 15, 20, 25, 30]
The Vector is: [10, 15, 20, 25, 30, 40]
Are both of them equal? false

```