# 用示例

在 Java 中堆叠 trimToSize()方法

> 原文:[https://www . geeksforgeeks . org/stack-trimtosize-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-trimtosize-method-in-java-with-example/)

Java 中**栈**的 **trimToSize()** 方法将栈实例的容量修剪为列表的当前容量。此方法用于将堆栈实例修剪到其包含的元素数量。

**语法:**

```
public void trimToSize()
```

**参数:**不接受任何参数。

**返回值:**不返回值。它将此堆栈实例的容量修剪为它包含的元素的数量。

下面的程序说明了 trimToSize()方法:

```
// Java code to demonstrate the working of
// trimToSize() method in Stack

// for Stack functions
import java.util.Stack;

public class GFG {
    public static void main(String[] args)
    {

        // Creating object of Stack<Integer>
        Stack<Integer>
            stack = new Stack<Integer>();

        // adding element to stack
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);

        // Print the Stack
        System.out.println("Stack: " + stack);

        // Print the current capacity of Stack
        System.out.println("Current capacity of Stack: "
                           + stack.capacity());

        // Change the capacity to 15
        stack.ensureCapacity(15);

        // Print the current capacity of Stack
        System.out.println("New capacity of Stack: "
                           + stack.capacity());

        // trims the capacity to the number of elements
        stack.trimToSize();

        // Print the current capacity of Stack
        System.out.println("Current capacity of Stack"
                           + " after use of trimToSize() method: "
                           + stack.capacity());
    }
}
```

**Output:**

```
Stack: [10, 20, 30, 40]
Current capacity of Stack: 10
New capacity of Stack: 20
Current capacity of Stack after use of trimToSize() method: 4

```

**例 2:**

```
// Java program to demonstrate
// Stack toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty Stack
        Stack<String> stack
            = new Stack<String>();

        // Use add() method
        // to add elements to the Collection
        stack.add("Welcome");
        stack.add("To");
        stack.add("Geeks");
        stack.add("For");
        stack.add("Geeks");

        // Print the Stack
        System.out.println("Stack: " + stack);

        // Print the current capacity of Stack
        System.out.println("Current capacity of Stack: "
                           + stack.capacity());

        // Change the capacity to 20
        stack.ensureCapacity(20);

        // Print the current capacity of Stack
        System.out.println("New capacity of Stack: "
                           + stack.capacity());

        // trims the capacity to the number of elements
        stack.trimToSize();

        // Print the current capacity of Stack
        System.out.println("Current capacity of Stack"
                           + " after use of trimToSize() method: "
                           + stack.capacity());
    }
}
```

**Output:**

```
Stack: [Welcome, To, Geeks, For, Geeks]
Current capacity of Stack: 10
New capacity of Stack: 20
Current capacity of Stack after use of trimToSize() method: 5

```