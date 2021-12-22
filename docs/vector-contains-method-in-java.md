# 向量包含 Java 中的()方法

> 原文:[https://www . geesforgeks . org/vector-contains-method-in-Java/](https://www.geeksforgeeks.org/vector-contains-method-in-java/)

**Java . util . vector . contains()**方法用于检查 Vector 中是否存在特定元素。所以基本上它是用来检查一个向量是否包含任何特定的元素。

**语法:**

```java
Vector.contains(Object element)
```

**参数:**该方法取一个强制参数 ***元素*** ，为向量类型。这是需要测试向量中是否存在的元素。

**返回值:**如果向量中存在元素，该方法返回 ***真*** ，否则返回**假**。

下面的程序说明了 Java.util.Vector.contains()方法:

**程序 1:**

```java
// Java code to illustrate contains()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("4");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Check for "Geeks" in the Vector
        System.out.println("Does the vector contains 'Geeks'? "
                           + vec_tor.contains("Geeks"));

        // Check for "4" in the Vector
        System.out.println("Does the Vector contains '4'? "
                           + vec_tor.contains("4"));

        // Check if the Queue contains "No"
        System.out.println("Does the Queue contains 'No'? "
                           + vec_tor.contains("No"));
    }
}
```

**Output:**

```java
Vector: [Welcome, To, Geeks, 4, Geeks]
Does the vector contains 'Geeks'? true
Does the Vector contains '4'? true
Does the Queue contains 'No'? false

```

**程序 2:**

```java
// Java code to illustrate contains()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements into the Vector
        vec_tor.add(10);
        vec_tor.add(15);
        vec_tor.add(30);
        vec_tor.add(20);
        vec_tor.add(5);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Check for "Geeks" in the Vector
        System.out.println("Does the vector contains 'Geeks'? "
                           + vec_tor.contains("Geeks"));

        // Check for "4" in the Vector
        System.out.println("Does the Vector contains '4'? "
                           + vec_tor.contains("4"));

        // Check if the vector contains "No"
        System.out.println("Does the Vector contains 'No'? "
                           + vec_tor.contains("No"));
    }
}
```

**Output:**

```java
Vector: [10, 15, 30, 20, 5]
Does the vector contains 'Geeks'? false
Does the Vector contains '4'? false
Does the Vector contains 'No'? false

```