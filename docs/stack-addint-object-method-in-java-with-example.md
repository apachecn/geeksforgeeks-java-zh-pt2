# Java 中的堆栈添加(int，Object)方法，示例

> 原文:[https://www . geesforgeks . org/stack-addint-object-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-addint-object-method-in-java-with-example/)

**堆栈类**的 **add(int，Object)** 方法在堆栈中的指定索引处插入一个元素。它将当前在该位置的元素(如果有)和任何后续元素向右移动(将通过添加一个来改变它们的索引)。

**语法:**

```
void add(int index, Object element)
```

**参数:**该方法接受如下所述的两个参数。

*   **索引:**要插入指定元素的索引。
*   **元素:**需要插入的元素。

**返回值:**此方法不返回值。

**异常:**如果指定的索引超出堆栈大小的范围，该方法将抛出**索引。**

下面的程序说明了 java.util.Stack.add(int index，Object element)方法的工作原理:

**示例:**

```
// Java code to illustrate boolean add(Object element)
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

        // Output the present Stack
        System.out.println("The Stack is: " + stack);

        // Adding new elements
        stack.add(2, "Last");
        stack.add(4, "Element");

        // Printing the new Stack
        System.out.println("The new Stack is: " + stack);
    }
}
```

**Output:**

```
The Stack is: [Geeks, for, Geeks, 10, 20]
The new Stack is: [Geeks, for, Last, Geeks, Element, 10, 20]

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

        // Output the present Stack
        System.out.println("The Stack is: "
                           + stack);

        // Adding new elements
        stack.add(0, 100);
        stack.add(3, 200);

        // Printing the new Stack
        System.out.println("The new Stack is: "
                           + stack);
    }
}
```

**Output:**

```
The Stack is: [10, 20, 30, 40, 50]
The new Stack is: [100, 10, 20, 200, 30, 40, 50]

```