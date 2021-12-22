# Java 中的堆栈列表迭代器()方法，示例

> 原文:[https://www . geesforgeks . org/stack-listiterator-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-listiterator-method-in-java-with-example/)

**Java.util.Stack** 类的**列表迭代器()**方法用于返回这个堆栈中元素的列表迭代器(按正确的顺序)。返回的列表迭代器是快速失败的。

**语法:**

```java
public ListIterator listIterator()
```

**返回值:**这个方法返回一个**列表迭代器**到这个堆栈中的元素上(按照正确的顺序)。

下面是说明*列表迭代器()*方法的例子。

**例 1:**

```java
// Java program to demonstrate
// listIterator() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
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

            // print stack
            System.out.println("Stack: "
                               + stack);

            // Creating object of ListIterator<String>
            // using listIterator() method
            ListIterator<String>
                iterator = stack.listIterator();

            // Printing the iterated value
            System.out.println("\nUsing ListIterator:\n");
            while (iterator.hasNext()) {
                System.out.println("Value is : "
                                   + iterator.next());
            }
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Stack: [A, B, C, D]

Using ListIterator:

Value is : A
Value is : B
Value is : C
Value is : D

```

**程序 2:**

```java
// Java code to illustrate lastIndexOf()
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

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Creating object of ListIterator<String>
        // using listIterator() method
        ListIterator<Integer>
            iterator = stack.listIterator();

        // Printing the iterated value
        System.out.println("\nUsing ListIterator:\n");
        while (iterator.hasNext()) {
            System.out.println("Value is : "
                               + iterator.next());
        }
    }
}
```

**Output:**

```java
Stack: [1, 2, 3, 10, 20]

Using ListIterator:

Value is : 1
Value is : 2
Value is : 3
Value is : 10
Value is : 20

```