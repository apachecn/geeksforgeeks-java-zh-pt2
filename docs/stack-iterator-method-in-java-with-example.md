# Java 中的堆栈迭代器()方法，示例

> 原文:[https://www . geesforgeks . org/stack-iterator-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-iterator-method-in-java-with-example/)

**Java . util . Stack . iterator()**方法用于返回一个与 Stack 元素相同的迭代器。元素从堆栈中随机返回。

**语法:**

```
Iterator *iterate_value* = Stack.iterator();

```

**参数:**函数不取任何参数。

**返回值:**方法迭代堆栈的元素并返回值(迭代器)。

下面的程序说明了 Java.util.Stack.iterator()方法的使用:

**例 1:**

```
// Java code to illustrate iterator()

import java.util.*;
import java.util.Stack;

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

        // Creating an iterator
        Iterator value = stack.iterator();

        // Displaying the values
        // after iterating through the stack
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```
Stack: [Welcome, To, Geeks, 4, Geeks]
The iterator values are: 
Welcome
To
Geeks
4
Geeks

```

**例 2:**

```
// Java code to illustrate hashCode()

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack
            = new Stack<Integer>();

        // Use add() method
        // to add elements into the Stack
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);
        stack.add(50);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Creating an iterator
        Iterator value = stack.iterator();

        // Displaying the values
        // after iterating through the stack
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```
Stack: [10, 20, 30, 40, 50]
The iterator values are: 
10
20
30
40
50

```