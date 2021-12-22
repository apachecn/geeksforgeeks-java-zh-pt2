# 用示例

在 Java 中堆叠 insertElementAt()方法

> 原文:[https://www . geesforgeks . org/stack-insertelementat-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-insertelementat-method-in-java-with-example/)

**Java . util . Stack . insertelementat(元素，索引)**方法用于在堆栈的指定索引处插入特定元素。元素和位置都作为参数传递。如果在指定的索引处插入一个元素，那么所有的元素都会被向上推一个，从而增加容量，为新元素创造空间。

**语法:**

```
Stack.insertElementAt()
```

**参数:**该方法接受两个参数:

*   **元素:**这是需要插入堆栈的元素。
*   **索引:**这是整数类型，指新元素要插入的位置。

**返回值:**该方法不返回任何内容。

**异常:**如果索引是无效数字，该方法将抛出**ArrayIndexOutOfBoundsException**。

下面的程序说明了 Java . util . stack . insertelementat()方法:

**程序 1:** 将字符串元素添加到堆栈中。

```
// Java code to illustrate insertElementAt()
import java.util.*;

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

        // Inseting element at 3rd position
        stack.insertElementAt("Hello", 2);

        // Inseting element at last position
        stack.insertElementAt("World", 6);

        // Displaying the final Stack
        System.out.println("The final Stack is "
                           + stack);
    }
}
```

**Output:**

```
Stack: [Welcome, To, Geeks, 4, Geeks]
The final Stack is [Welcome, To, Hello, Geeks, 4, Geeks, World]

```

**程序 2:** 向堆栈中添加整数元素。

```
// Java code to illustrate insertElementAt()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements into the Stack
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);
        stack.add(50);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Inseting element at 1st position
        stack.insertElementAt(100, 0);

        // Inseting element at fifth position
        stack.insertElementAt(200, 4);

        // Displaying the final Stack
        System.out.println("The final Stack is "
                           + stack);
    }
}
```

**Output:**

```
Stack: [10, 20, 30, 40, 50]
The final Stack is [100, 10, 20, 30, 200, 40, 50]

```