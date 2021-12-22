# Java 中的堆栈移除 All()方法，示例

> 原文:[https://www . geesforgeks . org/stack-remove all-in-Java-method-with-example/](https://www.geeksforgeeks.org/stack-removeall-method-in-java-with-example/)

**Java.util.Stack.removeAll(集合列)**方法用于从堆栈中移除指定集合中存在的所有元素。

**语法:**

```java
Stack.removeAll(Collection col)
```

**参数:**该方法接受一个强制参数**列**，它是要从堆栈中移除其元素的集合。

**返回值:**此方法返回**真**如果堆栈因操作而改变，否则**假**。

**异常:**如果指定的集合为空，该方法将抛出**空指针异常**。

下面的程序说明了方法:

**程序 1:**

```java
// Java code to illustrate removeAll()
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

        // Output the Stack
        System.out.println("Stack: " + stack);

        // Creating an empty Stack
        Stack<String> colstack = new Stack<String>();

        // Use add() method to add elements in the Stack
        colstack.add("Geeks");
        colstack.add("for");
        colstack.add("Geeks");

        // Remove the head using remove()
        boolean changed = stack.removeAll(colstack);

        // Print the result
        if (changed)
            System.out.println("Collection removed");
        else
            System.out.println("Collection not removed");

        // Print the final Stack
        System.out.println("Final Stack: " + stack);
    }
}
```

**Output:**

```java
Stack: [Geeks, for, Geeks, 10, 20]
Collection removed
Final Stack: [10, 20]

```

**程序 2:**

```java
// Java code to illustrate removeAll()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements in the Stack
        stack.add(1);
        stack.add(2);
        stack.add(3);
        stack.add(10);
        stack.add(20);

        // Output the Stack
        System.out.println("Stack: " + stack);

        // Creating an empty Stack
        Stack<Integer> colstack = new Stack<Integer>();

        // Use add() method to add elements in the Stack
        colstack.add(30);
        colstack.add(40);
        colstack.add(50);

        // Remove the head using remove()
        boolean changed = stack.removeAll(colstack);

        // Print the result
        if (changed)
            System.out.println("Collection removed");
        else
            System.out.println("Collection not removed");

        // Print the final Stack
        System.out.println("Final Stack: " + stack);
    }
}
```

**Output:**

```java
Stack: [1, 2, 3, 10, 20]
Collection not removed
Final Stack: [1, 2, 3, 10, 20]

```