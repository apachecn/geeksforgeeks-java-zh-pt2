# 用示例

在 Java 中堆叠克隆()方法

> 原文:[https://www . geeksforgeeks . org/stack-clone-in-Java-method-with-example/](https://www.geeksforgeeks.org/stack-clone-method-in-java-with-example/)

[堆栈类](https://www.geeksforgeeks.org/java-util-Stack-class-java/)的**克隆()**方法用于返回该堆栈的浅拷贝。它只是创建一个堆栈的副本。副本将引用内部数据阵列的克隆，但不引用原始内部数据阵列。

**语法:**

```java
Stack.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个对象，该对象只是堆栈的副本。

**异常:**如果对象的类不支持可克隆接口，这个方法抛出**克隆支持异常**。

下面的程序说明了 Java.util.Stack.clone()方法:

**程序 1:**

```java
// Java code to illustrate clone()

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

        // Creating another Stack to copy
        Object copy_Stack = stack.clone();

        // Displaying the copy of Stack
        System.out.println("The cloned Stack is: "
                           + copy_Stack);
    }
}
```

**Output:**

```java
Stack: [Welcome, To, Geeks, 4, Geeks]
The cloned Stack is: [Welcome, To, Geeks, 4, Geeks]

```

**程序 2:**

```java
// Java code to illustrate clone()

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements into the Queue
        stack.add(10);
        stack.add(15);
        stack.add(30);
        stack.add(20);
        stack.add(5);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Creating another Stack to copy
        Object copy_Stack = (Stack)stack.clone();

        // Displaying the copy of Stack
        System.out.println("The cloned Stack is: "
                           + copy_Stack);
    }
}
```

**Output:**

```java
Stack: [10, 15, 30, 20, 5]
The cloned Stack is: [10, 15, 30, 20, 5]

```