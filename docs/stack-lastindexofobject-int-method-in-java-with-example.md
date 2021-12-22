# 用示例

在 Java 中栈 lastIndexOf(Object，int)方法

> 原文:[https://www . geesforgeks . org/stack-last indexofobject-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-lastindexofobject-int-method-in-java-with-example/)

**Java . util . Stack . LastIndex of(Object 元素，int last_index)** 方法用于此堆栈中指定元素第一次出现的最后一个索引，从最后一个索引向前搜索，如果找不到该元素，则返回-1。更正式地说，返回最低的最后一个索引 I，例如(i > =最后一个索引& & Objects.equals(o，get(i))，如果没有这样的最后一个索引，则返回-1。

**语法:**

```
public int lastIndexOf(Object element, 
                        int last_index)
```

**参数:**该方法接受两个参数:

*   堆叠类型的**元素**。它指定需要在堆栈中检查其出现的元素。
*   **整数类型的最后一个索引**。它指定开始搜索的最后一个索引

**返回值:**这个方法从指定的最后一个索引返回元素在堆栈中第一次出现的最后一个索引或位置。否则，如果元素不在堆栈中，它将返回 **-1** 。返回值是整数类型。

**异常:**如果指定的索引大于或等于这个向量的当前大小，这个方法抛出**indexout of boundsexception**

下面的程序说明了 Java.util.Stack.lastIndexOf()方法:

**程序 1:**

```
// Java code to illustrate lastIndexOf()

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
                           + " of Geeks is at last index:"
                           + stack.indexOf("Geeks"));

        // Get the last occurrence of Geeks
        // using lastIndexOf() method
        System.out.println("The last occurrence"
                           + " of Geeks is at last index: "
                           + stack
                                 .lastIndexOf("Geeks",
                                              stack.lastIndexOf("Geeks")));
    }
}
```

**Output:**

```
Stack: [Geeks, for, Geeks, 10, Geeks]
The first occurrence of Geeks is at last index:0
The last occurrence of Geeks is at last index: 4

```

**程序 2:** 演示 IndexOutOfBoundsException

```
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

        // Get the 10th occurrence of Geeks
        // using lastIndexOf() method
        System.out.println("The 10th occurrence"
                           + " of Geeks is at index: ");

        try {
            stack.lastIndexOf("Geeks", 10);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Stack: [1, 2, 3, 10, 20]
The 10th occurrence of Geeks is at index: 
java.lang.IndexOutOfBoundsException: 10 >= 5

```