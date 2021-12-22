# 用示例

在 Java 中堆叠 addElement(E)方法

> 原文:[https://www . geesforgeks . org/stack-addelemente-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-addelemente-method-in-java-with-example/)

**堆栈类**的**添加元素(E)** 方法用于在堆栈末尾将作为参数传递的元素追加到该函数中。

**语法:**

```
boolean addElement(E obj)

Here, E is the type of elements maintained 
by this container.

```

**参数:**该函数接受一个参数 **E obj** ，该参数是要添加到堆栈末尾的对象。

**返回值:**如果至少执行了一个追加动作，则该方法返回*真*，否则返回*假*。

下面的程序说明了 Java.util.Stack.addElement()方法:

**例 1:**

```
// Java code to illustrate boolean addElement()

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

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // Appending "GeeksForGeeks" to the Stack
        stack.addElement("GeeksForGeeks");

        // Clearing the Stack using clear() and displaying
        System.out.println("The new Stack is: " + stack);
    }
}
```

**Output:**

```
The Stack is: [Geeks, for, Geeks, 10, 20]
The new Stack is: [Geeks, for, Geeks, 10, 20, GeeksForGeeks]

```

**例 2:**

```
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

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // Appending 100 to the Stack
        stack.addElement(100);

        // Clearing the Stack using clear() and displaying
        System.out.println("The new Stack is: " + stack);
    }
}
```

**Output:**

```
The Stack is: [10, 20, 30, 40, 50]
The new Stack is: [10, 20, 30, 40, 50, 100]

```