# 用示例

在 Java 中堆叠 setElementAt()方法

> 原文:[https://www . geesforgeks . org/stack-setelementat-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-setelementat-method-in-java-with-example/)

**Java 栈**的 **setElementAt()** 方法用于将该向量指定索引处的组件设置为指定对象。该位置的前一个组件将被丢弃。索引必须是大于或等于 0 且小于向量当前大小的值。

**语法:**

```
public void setElementAt(E element, int index)

```

**参数:**该函数接受两个参数，如上语法所示，如下所述。

*   **元素**:是替换现有元素的新元素，与栈的对象类型相同。
*   **索引**:这是整数类型，指的是堆栈中要替换的元素的位置。

**返回值:**这个方法不返回任何东西。

**异常:**如果索引超出范围(索引= size())，此方法将引发**arrayindextofboundsexception**

下面的程序说明了 Java.util.Stack.setElementAt()方法:

**例 1:**

```
// Java code to illustrate setElementAt()

import java.io.*;
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<String> stack
            = new Stack<String>();

        // Use add() method to add elements in the stack
        stack.add("Geeks");
        stack.add("for");
        stack.add("Geeks");
        stack.add("10");
        stack.add("20");

        // Displaying the linkedstack
        System.out.println("Stack:"
                           + stack);

        // Using setElementAt() method to replace Geeks with GFG
        stack.setElementAt("GFG", 2);
        System.out.println("Geeks replaced with GFG");

        // Displaying the modified linkedstack
        System.out.println("The new Stack is:"
                           + stack);
    }
}
```

**Output:**

```
Stack:[Geeks, for, Geeks, 10, 20]
Geeks replaced with GFG
The new Stack is:[Geeks, for, GFG, 10, 20]

```

**示例 2:** 演示 ArrayIndexOutOfBoundsException

```
// Java code to illustrate setElementAt()

import java.io.*;
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<String> stack
            = new Stack<String>();

        // Use add() method to add elements in the stack
        stack.add("Geeks");
        stack.add("for");
        stack.add("Geeks");
        stack.add("10");
        stack.add("20");

        // Displaying the linkedstack
        System.out.println("Stack:"
                           + stack);

        // Using setElementAt() method to replace 10th with GFG
        // and the 10th element does not exist
        System.out.println("Trying to replace 10th "
                           + "element with GFG");

        try {
            stack.setElementAt("GFG", 10);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Stack:[Geeks, for, Geeks, 10, 20]
Trying to replace 10th element with GFG
java.lang.ArrayIndexOutOfBoundsException: 10 >= 5

```