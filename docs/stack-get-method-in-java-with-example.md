# 用示例

在 Java 中堆叠 get()方法

> 原文:[https://www . geesforgeks . org/stack-get-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-get-method-in-java-with-example/)

**Java.util.Stack.get()** 方法用于从堆栈中获取或检索特定索引处的元素。

**语法:**

```
Stack.get(int index)
```

**参数:**该方法接受一个强制参数*索引*，该参数为整数数据类型。它指定要从堆栈中提取的元素的位置或索引。

**返回值:**该方法返回出现在参数索引指定位置的*元素*。

下面的程序说明了 Java.util.Stack.get()方法:

**程序 1** :

```
// Java code to illustrate get() method
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
        stack.add("20");

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Fetching the specific element from the Stack
        System.out.println("The element is: "
                           + stack.get(2));
    }
}
```

**Output:**

```
Stack: [Geeks, for, Geeks, 10, 20]
The element is: Geeks

```

**程序 2** :

```
// Java code to illustrate get() method
import java.util.Stack;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<String> stack = new Stack<String>();

        // Use add() method to add elements in the Stack
        stack.add("1");
        stack.add("2");
        stack.add("3");
        stack.add("10");
        stack.add("20");

        // Displaying the Stack
        System.out.println("Stack: "
                           + stack);

        // Fetching the specific element from the Stack
        System.out.println("The element is: "
                           + stack.get(4));
    }
}
```

**Output:**

```
Stack: [1, 2, 3, 10, 20]
The element is: 20

```