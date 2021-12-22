# Java 中的堆栈保证能力()方法，示例

> 原文:[https://www . geesforgeks . org/stack-ensurecapacity-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-ensurecapacity-method-in-java-with-example/)

**Java.util.Stack** 类的 **ensureCapacity()** 方法增加了这个 Stack 实例的容量(如果需要的话)，以确保它至少可以容纳最小容量参数指定的元素数量。

**语法:**

```
public void ensureCapacity(int minCapacity)
```

**参数:**该方法以**期望最小容量**为参数。

以下是说明**保证能力()**方法的例子。

**例 1:**

```
// Java program to demonstrate
// ensureCapacity() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
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
            System.out.println("Stack: "
                               + stack);

            // ensure that the Stack
            // can hold upto 5000 elements
            // using ensureCapacity() method
            stack.ensureCapacity(5000);

            // Print
            System.out.println("Stack can now"
                               + " surely store upto"
                               + " 5000 elements.");
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Stack: [10, 20, 30, 40]
Stack can now surely store upto 5000 elements.

```

**例 2:**

```
// Java program to demonstrate
// ensureCapacity() method for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
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

            // ensure that the Stack
            // can hold upto 400 elements
            // using ensureCapacity() method
            stack.ensureCapacity(400);

            // Print
            System.out.println("Stack can now"
                               + " surely store upto"
                               + " 400 elements.");
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Stack: [A, B, C, D]
Stack can now surely store upto 400 elements.

```