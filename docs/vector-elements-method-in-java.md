# Java 中的向量元素()方法

> 原文:[https://www . geesforgeks . org/vector-elements-method-in-Java/](https://www.geeksforgeeks.org/vector-elements-method-in-java/)

**T1。Java 中 Vector 类的 elements()** 方法用于获取 Vector 中存在的值的枚举。

**语法:**

```java
Enumeration enu = Vector.elements()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回向量值的 **[枚举](https://www.geeksforgeeks.org/enum-in-java/)** 。

下面的程序用来说明 java.util.Vector.elements()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate the elements() method
import java.util.*;

public class Vector_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>(5);

        // Inserting elements into the table
        vec_tor.add("Geeks");
        vec_tor.add("4");
        vec_tor.add("Geeks");
        vec_tor.add("Welcomes");
        vec_tor.add("You");

        // Displaying the Vector
        System.out.println("The Vector is: " + vec_tor);

        // Creating an empty enumeration to store
        Enumeration enu = vec_tor.elements();

        System.out.println("The enumeration of values are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**Output:**

```java
The Vector is: [Geeks, 4, Geeks, Welcomes, You]
The enumeration of values are:
Geeks
4
Geeks
Welcomes
You

```

**程序 2 :**

```java
import java.util.*;

public class Vector_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>(5);

        // Inserting elements into the table
        vec_tor.add(10);
        vec_tor.add(15);
        vec_tor.add(20);
        vec_tor.add(25);
        vec_tor.add(30);

        // Displaying the Vector
        System.out.println("The Vector is: " + vec_tor);

        // Creating an empty enumeration to store
        Enumeration enu = vec_tor.elements();

        System.out.println("The enumeration of values are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**Output:**

```java
The Vector is: [10, 15, 20, 25, 30]
The enumeration of values are:
10
15
20
25
30

```