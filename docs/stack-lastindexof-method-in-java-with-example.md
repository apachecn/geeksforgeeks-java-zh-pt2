# 用示例

在 Java 中堆叠 lastIndexOf()方法

> 原文:[https://www . geesforgeks . org/stack-last indexof-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-lastindexof-method-in-java-with-example/)

**Java.util.Stack.lastIndexOf(对象元素)**方法用于检查并查找堆栈中特定元素的出现。如果元素存在于堆栈中，则 lastIndexOf()方法返回元素最后一次出现的索引，否则返回-1。此方法用于查找堆栈中特定元素的最后一次出现。

**语法:**

```
Stack.lastIndexOf(Object element)
```

**参数:**参数*元素*为堆栈类型。它指的是需要检查最后一次出现的元素。

**返回值:**该方法返回元素在堆栈中最后一次出现的位置。如果元素不在堆栈中，则该方法返回-1。返回值是整数类型。

下面的程序说明了 Java.util.Stack.lastIndexOf()方法:

**程序 1:**

```
// Java code to illustrate lastIndexOf()
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

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // The last position of an element is returned
        System.out.println("Last occurrence of Geeks is at index: "
                           + stack.lastIndexOf("Geeks"));
        System.out.println("Last occurrence of 10 is at index: "
                           + stack.lastIndexOf("10"));
    }
}
```

**Output:**

```
Stack: [Geeks, for, Geeks, 10, 20]
Last occurrence of Geeks is at index: 2
Last occurrence of 10 is at index: 3

```

**程序 2:**

```
// Java code to illustrate lastIndexOf()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements in the Stack
        stack.add(10);
        stack.add(22);
        stack.add(3);
        stack.add(10);
        stack.add(20);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // The last position of an element is returned
        System.out.println("Last occurrence of 10 is at index: "
                           + stack.lastIndexOf(10));
        System.out.println("Last occurrence of 20 is at index: "
                           + stack.lastIndexOf(20));
    }
}
```

**Output:**

```
Stack: [10, 22, 3, 10, 20]
Last occurrence of 10 is at index: 3
Last occurrence of 20 is at index: 4

```