# Java 中方法的堆栈索引，示例

> 原文:[https://www . geeksforgeeks . org/stack-indexof-in-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-indexof-method-in-java-with-example/)

**Java . util . Stack . indexof(Object element)**方法用于检查并查找堆栈中特定元素的出现。如果该元素存在，则返回该元素第一次出现的索引，否则，如果堆栈不包含该元素，则返回-1。

**语法:**

```
Stack.indexOf(Object element)
```

**参数:**该方法接受堆栈类型的强制参数*元素*。它指定需要在堆栈中检查其出现的元素。

**返回值:**该方法返回元素在堆栈中第一次出现的索引或位置。否则，如果元素不在堆栈中，它将返回 **-1** 。返回值是整数类型。

下面的程序说明了 Java.util.Stack.indexOf()方法:

**程序 1:**

```
// Java code to illustrate indexOf()
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

        // The first position of an element
        // is returned
        System.out.println("The first occurrence"
                           + " of Geeks is at index:"
                           + stack.indexOf("Geeks"));
        System.out.println("The first occurrence"
                           + " of 10 is at index: "
                           + stack.indexOf("10"));
    }
}
```

**Output:**

```
Stack: [Geeks, for, Geeks, 10, 20]
The first occurrence of Geeks is at index:0
The first occurrence of 10 is at index: 3

```

**程序 2:**

```
// Java code to illustrate indexOf()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements in the Stack
        stack.add(1);
        stack.add(2);
        stack.add(3);
        stack.add(10);
        stack.add(20);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // The first position of an element
        // is returned
        System.out.println("The first occurrence"
                           + " of Geeks is at index:"
                           + stack.indexOf(2));
        System.out.println("The first occurrence"
                           + " of 10 is at index: "
                           + stack.indexOf(20));
    }
}
```

**Output:**

```
Stack: [1, 2, 3, 10, 20]
The first occurrence of Geeks is at index:1
The first occurrence of 10 is at index: 4

```