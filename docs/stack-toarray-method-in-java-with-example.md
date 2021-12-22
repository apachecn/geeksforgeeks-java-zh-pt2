# 用示例

在 Java 中堆叠到 Array()方法

> 原文:[https://www . geesforgeks . org/stack-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-toarray-method-in-java-with-example/)

Java 中**堆栈类**的 **toArray()** 方法用于形成一个与堆栈相同元素的数组。基本上，它将堆栈中的所有元素复制到一个新数组中。

**语法:**

```
Object[] arr = Stack.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含类似于堆栈元素的数组。

下面的程序说明了 Stack.toArray()方法:

**程序 1:**

```
// Java code to illustrate toArray()

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
        stack.add("For");
        stack.add("Geeks");

        // Displaying the Stack
        System.out.println("The Stack: " + stack);

        // Creating the array and using toArray()
        Object[] arr = stack.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The Stack: [Welcome, To, Geeks, For, Geeks]
The array is:
Welcome
To
Geeks
For
Geeks

```

**程序 2:**

```
// Java code to illustrate toArray()

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements into the Stack
        stack.add(10);
        stack.add(15);
        stack.add(30);
        stack.add(20);
        stack.add(5);
        stack.add(25);

        // Displaying the Stack
        System.out.println("The Stack: " + stack);

        // Creating the array and using toArray()
        Object[] arr = stack.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The Stack: [10, 15, 30, 20, 5, 25]
The array is:
10
15
30
20
5
25

```