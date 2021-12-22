# Java 中的堆栈大小()方法，示例

> 原文:[https://www . geeksforgeeks . org/stack-size-in-Java-method-with-example/](https://www.geeksforgeeks.org/stack-size-method-in-java-with-example/)

Java 中的 **Java.util.Stack.size()** 方法用于获取堆栈的大小或堆栈中存在的元素数量。

**语法:**

```
Stack.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回堆栈中存在的*大小或元素数量*。

下面的程序说明了 Java.util.Stack.size()方法:

**程序 1:** 用字符串元素堆叠。

```
// Java code to illustrate size()
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

        // Displaying the size of Stack
        System.out.println("The size is: " + stack.size());
    }
}
```

**Output:**

```
Stack: [Welcome, To, Geeks, 4, Geeks]
The size is: 5

```

**程序 2:** 用整数元素堆叠。

```
// Java code to illustrate size()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements into the Stack
        stack.add(10);
        stack.add(15);
        stack.add(30);
        stack.add(20);
        stack.add(5);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Displaying the size of Stack
        System.out.println("The size is: " + stack.size());
    }
}
```

**Output:**

```
Stack: [10, 15, 30, 20, 5]
The size is: 5

```