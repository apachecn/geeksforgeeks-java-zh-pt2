# 用示例

在 Java 中堆叠元素()方法

> 原文:[https://www . geesforgeks . org/stack-elements-in-Java-method-with-example/](https://www.geeksforgeeks.org/stack-elements-method-in-java-with-example/)

Java 中 Stack 类的**Java . util . Stack . elements()**方法用于获取 Stack 中存在的值的枚举。

**语法:**

```java
Enumeration enu = Stack.elements()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回堆栈值的 **[枚举](https://www.geeksforgeeks.org/enum-in-java/)** 。

下面的程序用来说明 java.util.Stack.elements()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate the elements() method
import java.util.*;

public class Stack_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Stack
        Stack<String> stack = new Stack<String>();

        // Inserting elements into the table
        stack.add("Geeks");
        stack.add("4");
        stack.add("Geeks");
        stack.add("Welcomes");
        stack.add("You");

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // Creating an empty enumeration to store
        Enumeration enu = stack.elements();

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
The Stack is: [Geeks, 4, Geeks, Welcomes, You]
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

public class Stack_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Inserting elements into the table
        stack.add(10);
        stack.add(15);
        stack.add(20);
        stack.add(25);
        stack.add(30);

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // Creating an empty enumeration to store
        Enumeration enu = stack.elements();

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
The Stack is: [10, 15, 20, 25, 30]
The enumeration of values are:
10
15
20
25
30

```