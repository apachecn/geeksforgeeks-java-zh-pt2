# 用示例

在 Java 中堆栈 addAll(int，Collection)方法

> 原文:[https://www . geesforgeks . org/stack-addallint-collection-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-addallint-collection-method-in-java-with-example/)

**堆栈类**的 **addAll(int，Collection)** 方法用于将集合中作为参数传递的所有元素追加到堆栈的特定索引或位置。

**语法:**

```
boolean addAll(int index, Collection C)
```

**参数:**该函数接受两个参数，如上语法所示，描述如下。

*   **索引**:该参数为整数数据类型，指定堆栈中从容器元素插入位置开始的位置。
*   **C** :是数组列表的集合。它是需要追加元素的集合。

**返回值:**如果至少执行了一个追加动作，则该方法返回*真*，否则返回*假*。

下面的程序说明了 Java.util.Stack.addAll()方法:

**例 1:**

```
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
        stack.addAll(1, c);

        // Clearing the Stack using clear() and displaying
        System.out.println("The new Stack is: " + stack);
    }
}
```

**Output:**

```
The Stack is: [Geeks, for, Geeks, 10, 20]
The new Stack is: [Geeks, A, Computer, Portal, for, Geeks, for, Geeks, 10, 20]

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

        // A collection is created
        Collection<Integer> c = new ArrayList<Integer>();
        c.add(1);
        c.add(2);
        c.add(3);

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // Appending the collection to the Stack
        stack.addAll(2, c);

        // Clearing the Stack using clear() and displaying
        System.out.println("The new Stack is: " + stack);
    }
}
```

**Output:**

```
The Stack is: [10, 20, 30, 40, 50]
The new Stack is: [10, 20, 1, 2, 3, 30, 40, 50]

```