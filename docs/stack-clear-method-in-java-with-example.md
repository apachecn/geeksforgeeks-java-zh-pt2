# 用示例

在 Java 中堆叠 clear()方法

> 原文:[https://www . geesforgeks . org/stack-clear-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-clear-method-in-java-with-example/)

方法用于从堆栈中移除所有元素。使用 clear()方法只会清除堆栈中的所有元素，而不会删除堆栈。换句话说，我们可以说 clear()方法仅用于清空现有的堆栈。

**语法:**

```java
Stack.clear()
```

**参数:**该方法不取任何参数

**返回值:**函数不返回值。

下面的程序说明了 Java.util.Stack.clear()方法。

**例 1:**

```java
// Java code to illustrate clear()
import java.util.*;

public class GFG {
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

        // Clearing the Stack using clear() method
        stack.clear();

        // Displaying the final Stack after clearing;
        System.out.println("The final Stack: " + stack);
    }
}
```

**Output:**

```java
Stack: [Welcome, To, Geeks, 4, Geeks]
The final Stack: []

```

**例 2:**

```java
// Java code to illustrate clear()
import java.util.*;

public class GFG {
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

        // Clearing the Stack using clear() method
        stack.clear();

        // Displaying the final Stack after clearing;
        System.out.println("The final Stack: " + stack);
    }
}
```

**Output:**

```java
Stack: [10, 15, 30, 20, 5]
The final Stack: []

```