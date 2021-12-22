# 用示例

在 Java 中堆叠 removeElementAt()方法

> 原文:[https://www . geesforgeks . org/stack-removeelementat-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-removeelementat-method-in-java-with-example/)

**Java . util . Stack . remove elementat(int index)**方法用于从堆栈中的特定位置或索引移除元素。在此过程中，在被移除的元素向下移动一个位置后，堆栈的大小会自动减少一个元素和所有其他元素。

**语法:**

```
Stack.removeElementAt(int index)
```

**参数:**该方法接受整数数据类型的强制参数**索引**，指定要从堆栈中移除的元素的位置。

**返回值:**此法有**空**返回类型。这意味着它不返回任何东西。

下面的程序说明了 Java . util . stack . remove(int index)方法:

**例 1:**

```
// Java code to illustrate removeElementAt()

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

        // Initial size
        System.out.println("The initial size is: "
                           + stack.size());

        // Remove the element at 3rd position
        stack.removeElementAt(2);

        // Print the final Stack
        System.out.println("Final Stack: " + stack);

        // Final size
        System.out.println("The final size is: "
                           + stack.size());
    }
}
```

**Output:**

```
Stack: [Geeks, for, Geeks, 10, 20]
The initial size is: 5
Final Stack: [Geeks, for, 10, 20]
The final size is: 4

```

**例 2:**

```
// Java code to illustrate removeElement() when position of
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

        // Initial size
        System.out.println("The initial size is: "
                           + stack.size());

        // Remove the element at 1st position
        stack.removeElementAt(0);

        // Print the final Stack
        System.out.println("Final Stack: " + stack);

        // Final size
        System.out.println("The final size is: "
                           + stack.size());
    }
}
```

**Output:**

```
Stack: [10, 20, 30, 40, 50]
The initial size is: 5
Final Stack: [20, 30, 40, 50]
The final size is: 4

```