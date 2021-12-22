# Java 中的堆栈移除等位()方法，示例

> 原文:[https://www . geesforgeks . org/stack-remove alliances-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-removeallelements-method-in-java-with-example/)

**Java . util . Stack . remove Alilements()**方法用于从此堆栈中移除所有组件，并将其大小设置为零。

**语法:**

```java
Stack.removeAllElements()
```

**参数:**该方法不取任何参数

**返回值:**函数不返回值。

下面的程序说明了 Java . util . stack . remove alloyments()方法。

**例 1:**

```java
// Java code to illustrate removeAllElements()
import java.util.*;

public class GFG {
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

        // removeAllElementsing the Stack
        // using removeAllElements() method
        stack.removeAllElements();

        // Displaying the final Stack after removeAllElementsing
        System.out.println("The final Stack: " + stack);
    }
}
```

**Output:**

```java
Stack: [Welcome, To, Geeks, 4, Geeks]
The final Stack: []

```

**例 2:**

```java
// Java code to illustrate removeAllElements()
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements into the Queue
        stack.add(10);
        stack.add(15);
        stack.add(30);
        stack.add(20);
        stack.add(5);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // removeAllElementsing the Stack
        // using removeAllElements() method
        stack.removeAllElements();

        // Displaying the final Stack after removeAllElementsing
        System.out.println("The final Stack: " + stack);
    }
}
```

**Output:**

```java
Stack: [10, 15, 30, 20, 5]
The final Stack: []

```