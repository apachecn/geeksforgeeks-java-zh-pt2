# Java 中的栈推()方法

> 原文:[https://www.geeksforgeeks.org/stack-push-method-in-java/](https://www.geeksforgeeks.org/stack-push-method-in-java/)

方法用于将一个元素推入堆栈。元素被推到堆栈的顶部。

**语法:**

```java
STACK.push(*E element*)
```

**参数:**该方法接受一个类型为 Stack 的参数*元素*，指的是要推入堆栈的元素。

**返回值:**该方法返回传递的参数。

下面的程序说明了 Java.util.Stack.push()方法:

**程序 1:** 将字符串元素添加到堆栈中。

```java
// Java code to illustrate push() method

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

        // Pushing elements into the stack
        STACK.push("Hello");
        STACK.push("World");

        // Displaying the final Stack
        System.out.println("Final Stack: " + STACK);
    }
}
```

**Output:**

```java
Initial Stack: [Welcome, To, Geeks, For, Geeks]
Final Stack: [Welcome, To, Geeks, For, Geeks, Hello, World]

```

**程序 2:** 向堆栈中添加整数元素。

```java
// Java code to illustrate push() method
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

        // Pushing elements into the Stack
        STACK.push(1254);
        STACK.push(4521);

        // Displaying the final Stack
        System.out.println("Final Stack: " + STACK);
    }
}
```

**Output:**

```java
Initial Stack: [10, 15, 30, 20, 5]
Final Stack: [10, 15, 30, 20, 5, 1254, 4521]

```