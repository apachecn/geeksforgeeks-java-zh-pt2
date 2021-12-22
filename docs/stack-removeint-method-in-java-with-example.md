# Java 中的栈移除(int)方法，示例

> 原文:[https://www . geesforgeks . org/stack-removeint-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-removeint-method-in-java-with-example/)

**Java . util . Stack . remove(*int index*)**方法用于从堆栈的特定位置或索引中移除元素。

**语法:**

```
Stack.remove(int index)
```

**参数:**该方法接受一个强制参数**索引**为整数数据类型，并指定要从堆栈中移除的元素的位置。

**返回值:**该方法返回刚从堆栈中移除的**元素**。

下面的程序说明了 Java . util . stack . remove(int index)方法:

**例 1:**

```
// Java code to illustrate remove() when position of
// element is passed as parameter

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

        // Output the Stack
        System.out.println("Stack: " + stack);

        // Remove the element using remove()
        String rem_ele = stack.remove(4);

        // Print the removed element
        System.out.println("Removed element: "
                           + rem_ele);

        // Print the final Stack
        System.out.println("Final Stack: "
                           + stack);
    }
}
```

**Output:**

```
Stack: [Geeks, for, Geeks, 10, 20]
Removed element: 20
Final Stack: [Geeks, for, Geeks, 10]

```

**例 2:**

```
// Java code to illustrate remove() when position of
// element is passed as parameter

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements in the Stack
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);
        stack.add(50);

        // Output the Stack
        System.out.println("Stack: " + stack);

        // Remove the element using remove()
        int rem_ele = stack.remove(0);

        // Print the removed element
        System.out.println("Removed element: "
                           + rem_ele);

        // Print the final Stack
        System.out.println("Final Stack: "
                           + stack);
    }
}
```

**Output:**

```
Stack: [10, 20, 30, 40, 50]
Removed element: 10
Final Stack: [20, 30, 40, 50]

```