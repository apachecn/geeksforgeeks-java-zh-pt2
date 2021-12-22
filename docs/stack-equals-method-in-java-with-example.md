# Java 中的 Stack equals()方法，示例

> 原文:[https://www . geesforgeks . org/stack-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-equals-method-in-java-with-example/)

Java 中 Stack 类的**Java . util . Stack . equals(Object obj)**方法用于验证对象与堆栈的相等性并进行比较。只有当两个堆栈包含具有相同顺序的相同元素时，列表才返回 true。

**语法:**

```java
first_Stack.equals(second_Stack)
```

**参数:**该方法接受一个强制参数 **second_Stack** ，该参数是指要与第一个 Stack 进行比较的第二个 Stack。

**返回值:**该方法返回**真**如果等式成立，并且对象和堆栈都相等，则返回**假**。

下面的程序用来说明 java.util.Stack.elements()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate the equals() method
import java.util.*;

public class Stack_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Stack
        Stack<String> stack1 = new Stack<String>();

        // Inserting elements into the table
        stack1.add("Geeks");
        stack1.add("4");
        stack1.add("Geeks");
        stack1.add("Welcomes");
        stack1.add("You");

        // Displaying the Stack
        System.out.println("The Stack is: "
                           + stack1);

        // Creating an empty Stack
        Stack<String> stack2 = new Stack<String>();

        // Inserting elements into the table
        stack2.add("Geeks");
        stack2.add("4");
        stack2.add("Geeks");
        stack2.add("Welcomes");
        stack2.add("You");

        // Displaying the Stack
        System.out.println("The Stack is: "
                           + stack2);

        System.out.println("Are both of them equal? "
                           + stack1.equals(stack2));
    }
}
```

**Output:**

```java
The Stack is: [Geeks, 4, Geeks, Welcomes, You]
The Stack is: [Geeks, 4, Geeks, Welcomes, You]
Are both of them equal? true

```

**程序 2 :**

```java
// Java code to illustrate the equals() method
import java.util.*;

public class Stack_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Stack
        Stack<Integer> stack1 = new Stack<Integer>();

        // Inserting elements into the table
        stack1.add(10);
        stack1.add(15);
        stack1.add(20);
        stack1.add(25);
        stack1.add(30);

        // Displaying the Stack
        System.out.println("The Stack is: " + stack1);

        // Creating an empty Stack
        Stack<Integer> stack2 = new Stack<Integer>();

        // Inserting elements into the table
        stack2.add(10);
        stack2.add(15);
        stack2.add(20);
        stack2.add(25);
        stack2.add(30);
        stack2.add(40);

        // Displaying the Stack
        System.out.println("The Stack is: " + stack2);

        System.out.println("Are both of them equal? "
                           + stack1.equals(stack2));
    }
}
```

**Output:**

```java
The Stack is: [10, 15, 20, 25, 30]
The Stack is: [10, 15, 20, 25, 30, 40]
Are both of them equal? false

```