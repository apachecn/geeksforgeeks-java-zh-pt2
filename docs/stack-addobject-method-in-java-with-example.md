# Java 中的堆栈添加(对象)方法，示例

> 原文:[https://www . geesforgeks . org/stack-addobject-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-addobject-method-in-java-with-example/)

**堆栈类**的 **add(Object)** 方法将指定的元素追加到该堆栈的末尾。

**语法:**

```java
boolean add(Object element)
```

**参数:**该函数接受单个参数**元素**，如上语法所示。由该参数指定的元素被追加到堆栈的末尾。

**返回值:**此方法成功执行后返回**真**，否则**假**。

下面的程序说明了 Java . util . stack . add(Object element)方法的工作原理:

**例 1:**

```java
// Java code to illustrate boolean add(Object element)
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<String> stack
            = new Stack<String>();

        // Use add() method
        // to add elements in the Stack
        stack.add("Geeks");
        stack.add("for");
        stack.add("Geeks");
        stack.add("10");
        stack.add("20");

        // Output the present Stack
        System.out.println("The Stack is: "
                           + stack);

        // Adding new elements to the end
        stack.add("Last");
        stack.add("Element");

        // Printing the new Stack
        System.out.println("The new Stack is: "
                           + stack);
    }
}
```

**Output:**

```java
The Stack is: [Geeks, for, Geeks, 10, 20]
The new Stack is: [Geeks, for, Geeks, 10, 20, Last, Element]

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

        // Output the present Stack
        System.out.println("The Stack is: "
                           + stack);

        // Adding new elements to the end
        stack.add(100);
        stack.add(200);

        // Printing the new Stack
        System.out.println("The new Stack is: "
                           + stack);
    }
}
```

**Output:**

```java
The Stack is: [10, 20, 30, 40, 50]
The new Stack is: [10, 20, 30, 40, 50, 100, 200]

```