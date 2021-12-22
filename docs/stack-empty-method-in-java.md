# Java 中栈空()方法

> 原文:[https://www.geeksforgeeks.org/stack-empty-method-in-java/](https://www.geeksforgeeks.org/stack-empty-method-in-java/)

java 中的 java.util.Stack.empty()方法用于检查堆栈是否为空。该方法为布尔类型，如果堆栈为空则返回 true，否则返回 false。

**语法:**

```
STACK.empty()
```

**参数:**该方法不取任何参数。

**返回值:**如果堆栈为空，则该方法返回布尔值 true，否则返回 false。

下面的程序说明了 java.util.Stack.empty()方法的工作:
**程序 1:**

```
// Java code to demonstrate empty() method
import java.util.*;

public class Stack_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Stack
        Stack<String> STACK = new Stack<String>();

        // Stacking strings
        STACK.push("Geeks");
        STACK.push("4");
        STACK.push("Geeks");
        STACK.push("Welcomes");
        STACK.push("You");

        // Displaying the Stack
        System.out.println("The stack is: " + STACK);

        // Checking for the emptiness of stack
        System.out.println("Is the stack empty? " + 
                                      STACK.empty());

        // Popping out all the elements
        STACK.pop();
        STACK.pop();
        STACK.pop();
        STACK.pop();
        STACK.pop();

        // Checking for the emptiness of stack
        System.out.println("Is the stack empty? " + 
                                     STACK.empty());
    }
}
```

**Output:**

```
The stack is: [Geeks, 4, Geeks, Welcomes, You]
Is the stack empty? false
Is the stack empty? true

```

**程序 2:**

```
// Java code to demonstrate empty() method
import java.util.*;

public class Stack_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Stack
        Stack<Integer> STACK = new Stack<Integer>();

        // Stacking int values
        STACK.push(8);
        STACK.push(5);
        STACK.push(9);
        STACK.push(2);
        STACK.push(4);

        // Displaying the Stack
        System.out.println("The stack is: " + STACK);

        // Checking for the emptiness of stack
        System.out.println("Is the stack empty? " + 
                                      STACK.empty());
    }
}
```

**Output:**

```
The stack is: [8, 5, 9, 2, 4]
Is the stack empty? false

```