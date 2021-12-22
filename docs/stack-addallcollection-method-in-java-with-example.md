# 用示例

在 Java 中堆叠 addAll(集合)方法

> 原文:[https://www . geeksforgeeks . org/stack-addall collection-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-addallcollection-method-in-java-with-example/)

**堆栈类**的 **addAll(Collection)** 方法用于将作为参数传递给此函数的集合中的所有元素追加到堆栈的末尾，记住集合迭代器的返回顺序。

**语法:**

```java
boolean addAll(Collection C)
```

**参数:**该方法接受一个强制参数 **C** ，它是数组列表的集合。它是一个集合，其元素需要追加到堆栈的末尾。

**返回值:**如果至少执行了一个追加动作，则该方法返回*真*，否则返回*假*。

下面的程序说明了 Java.util.Stack.addAll()方法:

```java
// Java code to illustrate boolean addAll()
import java.util.*;
import java.util.ArrayList;

public class GFG {
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

        // A collection is created
        Collection<String> c = new ArrayList<String>();
        c.add("A");
        c.add("Computer");
        c.add("Portal");
        c.add("for");
        c.add("Geeks");

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // Appending the collection to the Stack
        stack.addAll(c);

        // Clearing the Stack using clear() and displaying
        System.out.println("The new Stack is: " + stack);
    }
}
```

**Output:**

```java
The Stack is: [Geeks, for, Geeks, 10, 20]
The new Stack is: [Geeks, for, Geeks, 10, 20, A, Computer, Portal, for, Geeks]

```

**例 2:**

```java
// Java code to illustrate
// boolean add(Object element)

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<Integer> stack
            = new Stack<Integer>();

        // Use add() method
        // to add elements in the Stack
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);
        stack.add(50);

        // A collection is created
        Collection<Integer> c = new ArrayList<Integer>();
        c.add(1);
        c.add(2);
        c.add(3);

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // Appending the collection to the Stack
        stack.addAll(c);

        // Clearing the Stack using clear() and displaying
        System.out.println("The new Stack is: " + stack);
    }
}
```

**Output:**

```java
The Stack is: [10, 20, 30, 40, 50]
The new Stack is: [10, 20, 30, 40, 50, 1, 2, 3]

```