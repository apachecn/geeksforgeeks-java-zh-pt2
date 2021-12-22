# Java 中的堆栈容量()方法，示例

> 原文:[https://www . geesforgeks . org/stack-capacity-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-capacity-method-in-java-with-example/)

**栈类**的**容量()**方法用于获取该栈的容量。这是此堆栈容器中存在的元素数量。

**语法:**

```java
public int capacity()
```

**参数:**该函数接受一个参数 **E obj** ，该参数是要添加到堆栈末尾的对象。

**返回值:**该方法返回*整数值*，即堆栈的容量

下面的程序说明了 Java.util.Stack.capacity()方法:

**例 1:**

```java
// Java code to illustrate boolean capacity()

import java.util.*;
import java.util.ArrayList;

public class GFG {
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

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // checking capacity
        System.out.println("Capacity: "
                           + stack.capacity());
    }
}
```

**Output:**

```java
The Stack is: [Geeks, for, Geeks, 10, 20]
Capacity: 10

```

**例 2:**

```java
// Java code to illustrate
// boolean add(Object element)

import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<Integer> stack
            = new Stack<Integer>();

        // Use add() method
        // to add elements in the Stack
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);
        stack.add(50);

        // Displaying the Stack
        System.out.println("The Stack is: " + stack);

        // checking capacity
        System.out.println("Capacity: "
                           + stack.capacity());
    }
}
```

**Output:**

```java
The Stack is: [10, 20, 30, 40, 50]
Capacity: 10

```