# 用示例

在 Java 中堆叠 hashCode()方法

> 原文:[https://www . geesforgeks . org/stack-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-hashcode-method-in-java-with-example/)

Java 中的**Java . util . Stack . hashCode()**方法用来获取这个 Stack 的 hashcode 值。

**语法:**

```java
Stack.hashCode()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回该栈的**哈希码值**，该值为整数类型。

下面的程序说明了 Java.util.Stack.hashCode()方法:

**程序 1:** 用字符串元素堆叠。

```java
// Java code to illustrate hashCode()
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

        // Displaying the hashCode value of Stack
        System.out.println("The hashCode value is: "
                           + stack.hashCode());
    }
}
```

**Output:**

```java
Stack: [Welcome, To, Geeks, 4, Geeks]
The hashCode value is: -878886256

```

**程序 2:** 用整数元素堆叠。

```java
// Java code to illustrate hashCode()
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

        // Displaying the hashCode value of Stack
        System.out.println("The hashCode value is: "
                           + stack.hashCode());
    }
}
```

**Output:**

```java
Stack: [10, 20, 30, 40, 50]
The hashCode value is: 38490301

```