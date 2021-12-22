# Java 中的栈集()方法，示例

> 原文:[https://www . geesforgeks . org/stack-set-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-set-method-in-java-with-example/)

**Java 堆栈**的 **set()** 方法用于用另一个元素替换使用堆栈类创建的堆栈中的任何特定元素。这可以通过在 set()方法的参数中指定要替换的元素和新元素的位置来实现。

**语法:**

```java
public E set(int index, Object element)

```

**参数:**该函数接受两个参数，如上语法所示，如下所述。

*   **索引**:这是整数类型，指的是堆栈中要替换的元素的位置。
*   **元素**:是替换现有元素的新元素，与栈的对象类型相同。

**返回值:**该方法返回堆栈中被新值替换的前一个值。

**异常:**该方法抛出以下异常:

*   **不支持操作异常**:如果该堆栈不支持设置操作
*   **ClassCastException** :如果指定元素的类阻止其添加到该堆栈中
*   **NullPointRexception**:如果指定的元素为空，并且该堆栈不允许空元素
*   **IllegalArgumentException** :如果指定元素的某些属性阻止它被添加到这个堆栈中
*   **IndexOutOfBoundsException**:如果索引超出范围(索引=大小())

下面的程序说明了 Java.util.Stack.set()方法:

**例 1:**

```java
// Java code to illustrate set()

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

        // Using set() method to replace Geeks with GFG
        System.out.println("The Object that is replaced is: "
                           + stack.set(2, "GFG"));

        // Using set() method to replace 20 with 50
        System.out.println("The Object that is replaced is: "
                           + stack.set(4, "50"));

        // Displaying the modified linkedstack
        System.out.println("The new Stack is:"
                           + stack);
    }
}
```

**Output:**

```java
Stack:[Geeks, for, Geeks, 10, 20]
The Object that is replaced is: Geeks
The Object that is replaced is: 20
The new Stack is:[Geeks, for, GFG, 10, 50]

```

**示例 2:** 演示 IndexOutOfBoundException

```java
// Java code to illustrate set()

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

        // Using set() method to replace 10th with GFG
        // and the 10th element does not exist
        System.out.println("Trying to replace 10th "
                           + "element with GFG");

        try {
            stack.set(10, "GFG");
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Stack:[Geeks, for, Geeks, 10, 20]
Trying to replace 10th element with GFG
java.lang.ArrayIndexOutOfBoundsException: Array index out of range: 10

```