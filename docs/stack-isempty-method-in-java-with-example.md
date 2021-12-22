# 用示例

在 Java 中堆叠 isEmpty()方法

> 原文:[https://www . geesforgeks . org/stack-isempty-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-isempty-method-in-java-with-example/)

Java.util.Stack 。Java 中的 isEmpty()方法用于检查和验证堆栈是否为空。如果堆栈为空，则返回真，否则返回假。

**语法:**

```java
Stack.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**该函数返回*真*如果堆栈为空，则返回*假*。

下面的程序说明了 Java.util.Stack.isEmpty()方法:

**程序 1:**

```java
// Java code to illustrate isEmpty()
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
        System.out.println("Stack:  " + stack);

        // Verifying if the Stack is empty or not
        System.out.println("Is the Stack empty? "
                           + stack.isEmpty());

        // Clearing the Stack
        stack.clear();

        // Displaying the Stack
        System.out.println("Stack after clear(): "
                           + stack);

        // Verifying if the Stack is empty or not
        System.out.println("Is the Stack empty? "
                           + stack.isEmpty());
    }
}
```

**Output:**

```java
Stack:  [Welcome, To, Geeks, 4, Geeks]
Is the Stack empty? false
Stack after clear(): []
Is the Stack empty? true

```

**程序 2:**

```java
// Java code to illustrate isEmpty()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Displaying the Stack
        System.out.println("Stack:  " + stack);

        // Verifying if the Stack is empty or not
        System.out.println("Is the Stack empty? "
                           + stack.isEmpty());
    }
}
```

**Output:**

```java
Stack:  []
Is the Stack empty? true

```