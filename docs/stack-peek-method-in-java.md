# Java 中的栈 peek()方法

> 原文:[https://www.geeksforgeeks.org/stack-peek-method-in-java/](https://www.geeksforgeeks.org/stack-peek-method-in-java/)

java 中的 java.util.Stack.peek()方法用于检索或获取堆栈的第一个元素或堆栈顶部的元素。检索到的元素不会被删除或从堆栈中移除。

**语法:**

```java
STACK.peek()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回堆栈顶部的元素，否则如果堆栈为空，则返回空。

**异常:**如果堆栈为空，该方法抛出 *EmptyStackException* 。

下面的程序说明了 java.util.Stack.peek()方法:
**程序 1:**

```java
// Java code to illustrate peek() function

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<String> STACK = new Stack<String>();

        // Use push() to add elements into the Stack
        STACK.push("Welcome");
        STACK.push("To");
        STACK.push("Geeks");
        STACK.push("For");
        STACK.push("Geeks");

        // Displaying the Stack
        System.out.println("Initial Stack: " + STACK);

        // Fetching the element at the head of the Stack
        System.out.println("The element at the top of the"
                           + " stack is: " + STACK.peek());

        // Displaying the Stack after the Operation
        System.out.println("Final Stack: " + STACK);
    }
}
```

**Output:**

```java
Initial Stack: [Welcome, To, Geeks, For, Geeks]
The element at the top of the stack is: Geeks
Final Stack: [Welcome, To, Geeks, For, Geeks]

```

**程序 2:**

```java
// Java code to illustrate peek() function

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> STACK = new Stack<Integer>();

        // Use push() to add elements into the Stack
        STACK.push(10);
        STACK.push(15);
        STACK.push(30);
        STACK.push(20);
        STACK.push(5);

        // Displaying the Stack
        System.out.println("Initial Stack: " + STACK);

        // Fetching the element at the head of the Stack
        System.out.println("The element at the top of the"
                           + " stack is: " + STACK.peek());

        // Displaying the Stack after the Operation
        System.out.println("Final Stack: " + STACK);
    }
}
```

**Output:**

```java
Initial Stack: [10, 15, 30, 20, 5]
The element at the top of the stack is: 5
Final Stack: [10, 15, 30, 20, 5]

```