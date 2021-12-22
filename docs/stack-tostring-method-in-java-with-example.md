# 用示例

在 Java 中堆叠 toString()方法

> 原文:[https://www . geesforgeks . org/stack-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-tostring-method-in-java-with-example/)

**Java 堆栈**的 **toString()** 方法用于返回集合元素的字符串表示。

字符串表示包括集合元素的集合表示，其顺序由方括号[]中的迭代器选取。此方法主要用于在字符串表示形式中显示字符串类型以外的集合(例如:对象、整数)。

**语法:**

```
public String toString()
```

**参数**该方法不取任何参数。

**返回**该方法返回集合的**字符串表示**。

以下示例说明了 toString()方法:

**例 1:**

```
// Java program to demonstrate
// Stack toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty Stack
        Stack<String> stack
            = new Stack<String>();

        // Use add() method
        // to add elements to the Collection
        stack.add("Welcome");
        stack.add("To");
        stack.add("Geeks");
        stack.add("For");
        stack.add("Geeks");

        // Using toString() method
        System.out.println(stack.toString());
    }
}
```

**Output:**

```
[Welcome, To, Geeks, For, Geeks]

```

**例 2:**

```
// Java program to demonstrate
// Stack toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty Stack
        Stack<Integer> stack
            = new Stack<Integer>();

        // Use add() method
        // to add elements to the Collection
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);

        // Using toString() method
        System.out.println(stack.toString());
    }
}
```

**Output:**

```
[10, 20, 30, 40]

```