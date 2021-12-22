# 栈包含 Java 中的 All()方法，示例

> 原文:[https://www . geesforgeks . org/stack-contains all-in-Java-method-with-example/](https://www.geeksforgeeks.org/stack-containsall-method-in-java-with-example/)

**Java 栈**的 **containsAll()** 方法用于检查两个栈是否包含相同的元素。它将一个堆栈作为参数，如果该堆栈的所有元素都存在于另一个堆栈中，则返回 True。

**语法:**

```
public boolean containsAll(Collection C)
```

**参数:**参数 *C* 为集合。此参数指的是需要在此堆栈中检查其元素出现的堆栈。

**返回值:**如果这个*栈*包含其他栈的所有元素，方法返回真，否则返回假。

下面的程序说明了 Stack.containsAll()方法:

**程序 1:**

```
// Java code to illustrate
// Stack containsAll()

import java.util.*;

class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty stack
        Stack<String>
            stack = new Stack<String>();

        // Use add() method to
        // add elements in the stack
        stack.add("Geeks");
        stack.add("for");
        stack.add("Geeks");
        stack.add("10");
        stack.add("20");

        // prints the stack
        System.out.println("Stack 1: "
                           + stack);

        // Creating another empty stack
        Stack<String>
            stack2 = new Stack<String>();

        // Use add() method to
        // add elements in the stack
        stack2.add("Geeks");
        stack2.add("for");
        stack2.add("Geeks");
        stack2.add("10");
        stack2.add("20");

        // prints the stack
        System.out.println("Stack 2: "
                           + stack2);

        // Check if the stack
        // contains same elements
        System.out.println("\nDoes stack 1 contains stack 2: "
                           + stack.containsAll(stack2));
    }
}
```

**Output:**

```
Stack 1: [Geeks, for, Geeks, 10, 20]
Stack 2: [Geeks, for, Geeks, 10, 20]

Does stack 1 contains stack 2: true

```

**程序 2:**

```
// Java code to illustrate boolean containsAll()

import java.util.*;

class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty stack
        Stack<String>
            stack = new Stack<String>();

        // Use add() method to
        // add elements in the stack
        stack.add("Geeks");
        stack.add("for");
        stack.add("Geeks");

        // prints the stack
        System.out.println("Stack 1: "
                           + stack);

        // Creating another empty stack
        Stack<String>
            stack2 = new Stack<String>();

        // Use add() method to
        // add elements in the stack
        stack2.add("10");
        stack2.add("20");

        // prints the stack
        System.out.println("Stack 2: "
                           + stack2);

        // Check if the stack
        // contains same elements
        System.out.println("\nDoes stack 1 contains stack 2: "
                           + stack.containsAll(stack2));
    }
}
```

**Output:**

```
Stack 1: [Geeks, for, Geeks]
Stack 2: [10, 20]

Does stack 1 contains stack 2: false

```