# Java 中的堆栈元素 At()方法，示例

> 原文:[https://www . geesforgeks . org/stack-element at-in-Java-method-with-example/](https://www.geeksforgeeks.org/stack-elementat-method-in-java-with-example/)

**Java . util . Stack . elementat(*int pos*)**方法用于从堆栈中获取或检索特定索引处的元素。

**语法:**

```
Stack.elementAt(int pos)
```

**参数:**该方法接受整数数据类型的强制参数*位置*，指定要从堆栈中提取的元素的位置或索引。

**返回值:**该方法返回出现在参数*位置*指定位置的*元素*。

下面的程序说明了 Java.util.Stack.get()方法:

**程序 1:**

```
// Java code to illustrate elementAt() method
import java.util.Stack;

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
        System.out.println("Stack: "
                           + stack);

        // Fetching the specific element from the Stack
        System.out.println("The element is: "
                           + stack.elementAt(3));
    }
}
```

**Output:**

```
Stack: [Geeks, for, Geeks, 10, 20]
The element is: 10

```

**程序 2:**

```
// Java code to illustrate elementAt() method
import java.util.Stack;

public class StackDemo {
    public static void main(String args[])
    {

        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements in the Stack
        stack.add(1);
        stack.add(2);
        stack.add(3);
        stack.add(4);
        stack.add(5);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Fetching the specific element from the Stack
        System.out.println("The element is: "
                           + stack.elementAt(1));
    }
}
```

**Output:**

```
Stack: [1, 2, 3, 4, 5]
The element is: 2

```