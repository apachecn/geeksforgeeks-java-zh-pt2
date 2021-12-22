# 用示例

堆叠 Java 中的 lastElement()方法

> 原文:[https://www . geesforgeks . org/stack-last element-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-lastelement-method-in-java-with-example/)

Java 中的**Java . util . Stack . LastElement()**方法用于检索或获取堆栈的最后一个元素。它返回堆栈最后一个索引处的元素。

**语法:**

```java
Stack.lastElement()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回堆栈中最后一个元素**。**

**下面的程序说明了 Java.util.Stack.lastElement()方法:**

****程序 1:****

```java
// Java code to illustrate lastElement()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<String> stack = new Stack<String>();

        // Use add() method to add elements into the Stack
        stack.add("Welcome");
        stack.add("To");
        stack.add("Geeks");
        stack.add("4");
        stack.add("Geeks");

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Displaying the last element
        System.out.println("The last element is: "
                           + stack.lastElement());
    }
}
```

****Output:**

```java
Stack: [Welcome, To, Geeks, 4, Geeks]
The last element is: Geeks

```** 

****程序 2:****

```java
// Java code to illustrate lastElement()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements into the Stack
        stack.add(10);
        stack.add(15);
        stack.add(30);
        stack.add(20);
        stack.add(5);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Displaying the last element
        System.out.println("The last element is: "
                           + stack.lastElement());
    }
}
```

****Output:**

```java
Stack: [10, 15, 30, 20, 5]
The last element is: 5

```**