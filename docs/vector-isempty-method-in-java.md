# Java 中的 Vector isEmpty()方法

> 原文:[https://www . geesforgeks . org/vector-isempty-method-in-Java/](https://www.geeksforgeeks.org/vector-isempty-method-in-java/)

Java.util.Vector 。Java 中的 isEmpty()方法用于检查和验证 Vector 是否为空。如果向量为空，则返回真，否则返回假。

**语法:**

```java
Vector.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**该函数返回*真*如果向量为空，则返回*假*。

下面的程序说明了 Java.util.Vector.isEmpty()方法:

**程序 1:**

```java
// Java code to illustrate isEmpty()
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
        System.out.println("Vector:  " + vec_tor);

        // Verifying if the Vector is empty or not
        System.out.println("Is the Vector empty? "
                           + vec_tor.isEmpty());

        // Clearing the Vector
        vec_tor.clear();

        // Displaying the Vector
        System.out.println("Vector after clear(): "
                           + vec_tor);

        // Verifying if the Vector is empty or not
        System.out.println("Is the Vector empty? "
                           + vec_tor.isEmpty());
    }
}
```

**Output:**

```java
Vector:  [Welcome, To, Geeks, 4, Geeks]
Is the Vector empty? false
Vector after clear(): []
Is the Vector empty? true

```

**程序 2:**

```java
// Java code to illustrate isEmpty()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Displaying the Vector
        System.out.println("Vector:  " + vec_tor);

        // Verifying if the Vector is empty or not
        System.out.println("Is the Vector empty? "
                           + vec_tor.isEmpty());
    }
}
```

**Output:**

```java
Vector:  []
Is the Vector empty? true

```