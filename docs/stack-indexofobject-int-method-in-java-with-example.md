# Java 中(Object，int)方法的堆栈索引，示例

> 原文:[https://www . geesforgeks . org/stack-indexofobject-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-indexofobject-int-method-in-java-with-example/)

**Java . util . Stack . indexof(Object 元素，int index)** 方法用于此堆栈中指定元素第一次出现的索引，从索引向前搜索，如果找不到该元素，则返回-1。更正式地说，返回最低的指数 I，例如(i > =指数& & Objects.equals(o，get(i))，如果没有这样的指数，则返回-1。

**语法:**

```java
public int indexOf(Object element, 
                        int index)
```

**参数:**该方法接受两个参数:

*   堆叠类型的**元素**。它指定需要在堆栈中检查其出现的元素。
*   **整数类型的索引**。它指定开始搜索的索引

**返回值:**这个方法从指定的索引返回元素在堆栈中第一次出现的索引或位置。否则，如果元素不在堆栈中，它将返回 **-1** 。返回值是整数类型。

**异常:**如果指定的指数为负，该方法抛出**指数。**

下面的程序说明了 Java.util.Stack.indexOf()方法:

**程序 1:**

```java
// Java code to illustrate indexOf()

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
        stack.add("Geeks");

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // The first position of an element
        // is returned
        System.out.println("The first occurrence"
                           + " of Geeks is at index:"
                           + stack.indexOf("Geeks"));

        // Get the second occurrence of Geeks
        // using indexOf() method
        System.out.println("The second occurrence"
                           + " of Geeks is at index: "
                           + stack.indexOf("Geeks",
                                           stack.indexOf("Geeks")));
    }
}
```

**Output:**

```java
Stack: [Geeks, for, Geeks, 10, Geeks]
The first occurrence of Geeks is at index:0
The second occurrence of Geeks is at index: 0

```

**程序 2:** 演示 IndexOutOfBoundsException

```java
// Java code to illustrate indexOf()
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

        // Get the -1 occurrence of Geeks
        // using indexOf() method
        System.out.println("The -1 occurrence"
                           + " of Geeks is at index: ");

        try {
            stack.indexOf("Geeks",
                          stack.indexOf("Geeks"));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Stack: [1, 2, 3, 10, 20]
The -1 occurrence of Geeks is at index: 
java.lang.ArrayIndexOutOfBoundsException: -1

```