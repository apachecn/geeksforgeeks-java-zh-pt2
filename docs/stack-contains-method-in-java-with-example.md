# 栈包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/stack-contains-in-Java-method-with-example/](https://www.geeksforgeeks.org/stack-contains-method-in-java-with-example/)

**Java . util . Stack . contains()**方法用于检查堆栈中是否存在特定元素。所以基本上它是用来检查一个堆栈是否包含任何特定的元素。

**语法:**

```
Stack.contains(Object element)
```

**参数:**该方法取一个强制参数 ***元素*** ，类型为 Stack。这是需要测试堆栈中是否存在的元素。

**返回值:**如果元素存在于堆栈中，该方法返回 ***真*** ，否则返回**假**。

下面的程序说明了 Java.util.Stack.contains()方法:

**程序 1:**

```
// Java code to illustrate contains()
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

        // Check for "Geeks" in the Stack
        System.out.println("Does the Stack contains 'Geeks'? "
                           + stack.contains("Geeks"));

        // Check for "4" in the Stack
        System.out.println("Does the Stack contains '4'? "
                           + stack.contains("4"));

        // Check if the Queue contains "No"
        System.out.println("Does the Stack contains 'No'? "
                           + stack.contains("No"));
    }
}
```

**Output:**

```
Stack: [Welcome, To, Geeks, 4, Geeks]
Does the Stack contains 'Geeks'? true
Does the Stack contains '4'? true
Does the Stack contains 'No'? false

```

**程序 2:**

```
// Java code to illustrate contains()
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

        // Check for "Geeks" in the Stack
        System.out.println("Does the Stack contains 'Geeks'? "
                           + stack.contains("Geeks"));

        // Check for "4" in the Stack
        System.out.println("Does the Stack contains '4'? "
                           + stack.contains("4"));

        // Check if the Stack contains "No"
        System.out.println("Does the Stack contains 'No'? "
                           + stack.contains("No"));
    }
}
```

**Output:**

```
Stack: [10, 15, 30, 20, 5]
Does the Stack contains 'Geeks'? false
Does the Stack contains '4'? false
Does the Stack contains 'No'? false

```