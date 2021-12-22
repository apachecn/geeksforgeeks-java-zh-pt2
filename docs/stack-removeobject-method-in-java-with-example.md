# Java 中的堆栈移除(对象)方法，示例

> 原文:[https://www . geesforgeks . org/stack-remove object-in-Java-method-with-example/](https://www.geeksforgeeks.org/stack-removeobject-method-in-java-with-example/)

**Java . util . Stack . remove(的*对象)***方法用于从堆栈中移除任何特定元素。

**语法:**

```java
Stack.remove(Object o)
```

**参数:**该方法接受一个强制参数 **o** 是堆栈的对象类型，并指定要从堆栈中移除的元素。

**返回值:**如果找到指定元素并从堆栈中移除，则返回**真**，否则返回**假**。

下面的程序说明了 Java.util.Stack.remove(对象 o)方法:

**例 1:**

```java
// Java code to illustrate remove() when position of
// element is passed as parameter

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<String> stack = new Stack<String>();

        // Use add() method to add elements in the Stack
        stack.add("Geeks");
        stack.add("for");
        stack.add("Geeks");
        stack.add("10");
        stack.add("20");

        // Output the Stack
        System.out.println("Stack: " + stack);

        // Remove the element using remove()
        boolean res = stack.remove("20");

        // Print the removed element
        System.out.println("Was 20 removed: "
                           + res);

        // Print the final Stack
        System.out.println("Final Stack: "
                           + stack);
    }
}
```

**Output:**

```java
Stack: [Geeks, for, Geeks, 10, 20]
Was 20 removed: true
Final Stack: [Geeks, for, Geeks, 10]

```

**例 2:**

```java
// Java code to illustrate remove() when position of
// element is passed as parameter

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements in the Stack
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);
        stack.add(50);

        // Output the Stack
        System.out.println("Stack: " + stack);

        // Remove the element using remove()
        boolean res = stack.remove("100");

        // Print the removed element
        System.out.println("Was 100 removed: "
                           + res);

        // Print the final Stack
        System.out.println("Final Stack: "
                           + stack);
    }
}
```

**Output:**

```java
Stack: [10, 20, 30, 40, 50]
Was 100 removed: false
Final Stack: [10, 20, 30, 40, 50]

```