# Java 中的栈 pop()方法

> 原文:[https://www.geeksforgeeks.org/stack-pop-method-in-java/](https://www.geeksforgeeks.org/stack-pop-method-in-java/)

Java 中的 Java.util.Stack.pop()方法用于从堆栈中弹出一个元素。元素从堆栈顶部弹出，并从堆栈中移除。
**语法:**

```
STACK.pop()
```

**参数:**该方法不取任何参数。
**返回值:**这个方法返回堆栈顶部的元素，然后移除它。
**异常:**该方法抛出 *EmptyStackException* 如果堆栈为空则抛出。
下面的程序说明了 Java.util.Stack.pop()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate pop()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<String> STACK = new Stack<String>();

        // Use add() method to add elements
        STACK.push("Welcome");
        STACK.push("To");
        STACK.push("Geeks");
        STACK.push("For");
        STACK.push("Geeks");

        // Displaying the Stack
        System.out.println("Initial Stack: " + STACK);

        // Removing elements using pop() method
        System.out.println("Popped element: " +
                                         STACK.pop());
        System.out.println("Popped element: " +
                                         STACK.pop());

        // Displaying the Stack after pop operation
        System.out.println("Stack after pop operation "
                                             + STACK);
    }
}
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate pop()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> STACK = new Stack<Integer>();

        // Use add() method to add elements
        STACK.push(10);
        STACK.push(15);
        STACK.push(30);
        STACK.push(20);
        STACK.push(5);

        // Displaying the Stack
        System.out.println("Initial Stack: " + STACK);

        // Removing elements using pop() method
        System.out.println("Popped element: " +
                                         STACK.pop());
        System.out.println("Popped element: " +
                                         STACK.pop());

        // Displaying the Stack after pop operation
        System.out.println("Stack after pop operation "
                                             + STACK);
    }
}
```

**Output:** 

```
Initial Stack: [10, 15, 30, 20, 5]
Popped element: 5
Popped element: 20
Stack after pop operation [10, 15, 30]
```