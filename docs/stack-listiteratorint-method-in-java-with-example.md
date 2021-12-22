# Java 中堆栈列表迭代器(int)方法，示例

> 原文:[https://www . geesforgeks . org/stack-listiteratorint-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-listiteratorint-method-in-java-with-example/)

**堆栈类**的**列表迭代器(int)** 方法用于从列表中的指定位置开始，返回列表中元素的列表迭代器(按适当的顺序)。指定的索引指示对 next 的初始调用将返回的第一个元素。对 previous 的初始调用将返回具有指定索引减 1 的元素。返回的列表迭代器是快速失败的。

**语法:**

```java
public ListIterator listIterator(int index)
```

**参数:**该方法将第一个元素的**索引作为从列表迭代器返回的参数(通过调用 next)**

**返回值:**这个方法从列表中的指定位置开始，在这个列表中的元素上返回一个**列表迭代器**。

**异常:**如果索引超出范围(索引大小())，该方法抛出**indexout of boundsexception**。

下面是说明**列表迭代器()**方法的例子。

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
            Stack<String> stack = new Stack<String>();

            // adding element to stack
            stack.add("A");
            stack.add("B");
            stack.add("C");
            stack.add("D");

            // print stack
            System.out.println("Stack: "
                               + stack);

            // getting iterated value starting from index 2
            // using listIterator() method
            ListIterator<String>
                iterator = stack.listIterator(2);

            // Printing the iterated value
            System.out.println("\nUsing ListIterator"
                               + " from Index 2:\n");
            while (iterator.hasNext()) {
                System.out.println("Value is : "
                                   + iterator.next());
            }
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Stack: [A, B, C, D]

Using ListIterator from Index 2:

Value is : C
Value is : D

```

**示例 2:** 适用于*指数出界异常*

```java
// Java program to demonstrate
// listIterator() method
// for IndexOutOfBoundsException

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
            System.out.println("Size of Stack: "
                               + stack.size());

            // Get ListIterator from index 7
            // using listIterator() method
            System.out.println("Trying to getListIterator"
                               + " from index 7\n");

            ListIterator<String>
                iterator = stack.listIterator(7);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Stack: [A, B, C, D]
Size of Stack: 4
Trying to getListIterator from index 7

Exception thrown : java.lang.IndexOutOfBoundsException: Index: 7

```