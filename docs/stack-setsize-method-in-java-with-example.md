# 用示例

在 Java 中堆叠 setSize()方法

> 原文:[https://www . geesforgeks . org/stack-setsize-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-setsize-method-in-java-with-example/)

**Java.util.Stack** 类的 **setSize()** 方法将此 Stack 实例的大小更改为作为参数传递的大小。

**语法:**

```java
public void setSize(int size)
```

**参数:**该方法以**新尺寸**为参数。

**异常:**如果新大小为负，该方法抛出**arrayindextofboundsexception**。

以下是说明**设置大小()**方法的例子。

**例 1:**

```java
// Java program to demonstrate
// setSize() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        try {

            // Creating object of Stack<Integer>
            Stack<Integer>
                stack = new Stack<Integer>();

            // adding element to stack
            stack.add(10);
            stack.add(20);
            stack.add(30);
            stack.add(40);

            // Print the Stack
            System.out.println("Stack: " + stack);

            // Print the current size of Stack
            System.out.println("Current size of Stack: "
                               + stack.size());

            // Change the size to 10
            stack.setSize(10);

            // Print the current size of Stack
            System.out.println("New size of Stack: "
                               + stack.size());
        }

        catch (Exception e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Stack: [10, 20, 30, 40]
Current size of Stack: 4
New size of Stack: 10

```

**例 2:**

```java
// Java program to demonstrate
// setSize() method for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        try {

            // Creating object of Stack<Integer>
            Stack<String>
                stack = new Stack<String>();

            // adding element to stack
            stack.add("A");
            stack.add("B");
            stack.add("C");
            stack.add("D");

            // Print the Stack
            System.out.println("Stack: "
                               + stack);

            // Print the current size of Stack
            System.out.println("Current size of Stack: "
                               + stack.size());

            // Change the size to -1
            stack.setSize(-1);

            // Print the current size of Stack
            System.out.println("New size of Stack: "
                               + stack.size());
        }

        catch (Exception e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Stack: [A, B, C, D]
Current size of Stack: 4
Exception thrown : java.lang.ArrayIndexOutOfBoundsException: -1

```