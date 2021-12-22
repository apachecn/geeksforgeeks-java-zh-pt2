# 用示例

在 Java 中堆叠 copyInto()方法

> 原文:[https://www . geesforgeks . org/stack-copy into-in-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-copyinto-method-in-java-with-example/)

**Java . util . Stack . copy into()**方法用于将该 Stack 的所有组件复制到另一个 Stack，有足够的空间容纳该 Stack 的所有组件。需要注意的是，元素的索引保持不变。堆栈中的元素被堆栈的元素替换。

**语法:**

```
Stack.copyInto(Object Stack[])
```

**参数:**参数**栈[**属于栈的类型。这是要将堆栈元素复制到的堆栈。

**返回值:**该方法为 **void** 类型，不返回值。

**异常:**如果堆栈为空，该方法将抛出**空指针异常**。

下面的程序说明了 Java.util.Stack.copyInto()方法:

**程序 1:**

```
// Java code to illustrate copyInto()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<String> stack = new Stack<String>();

        // Use add() method to add elements into the Stack
        stack.add("Welcome");
        stack.add("To");
        stack.add("Geeks");
        stack.add("4");
        stack.add("Geeks");

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Creating an Stack
        String arr[] = new String[6];

        arr[0] = "Hello";
        arr[1] = "World";

        // Displaying the initial Stack
        System.out.println("The initial Stack is: ");
        for (String str : arr)
            System.out.println(str);

        // Copying
        stack.copyInto(arr);

        // The final Stack
        System.out.println("The final Stack is: ");
        for (String str : arr)
            System.out.println(str);
    }
}
```

**Output:**

```
Stack: [Welcome, To, Geeks, 4, Geeks]
The initial Stack is: 
Hello
World
null
null
null
null
The final Stack is: 
Welcome
To
Geeks
4
Geeks
null

```

**程序 2:**

```
// Java code to illustrate copyInto()
import java.util.*;

public class StackDemo {
    public static void main(String args[])
    {
        // Creating an empty Stack
        Stack<Integer> stack = new Stack<Integer>();

        // Use add() method to add elements into the Stack
        stack.add(10);
        stack.add(20);
        stack.add(30);
        stack.add(40);
        stack.add(50);

        // Displaying the Stack
        System.out.println("Stack: " + stack);

        // Creating an Stack
        Integer arr[] = new Integer[6];

        arr[0] = 50;
        arr[1] = 60;
        arr[2] = 70;
        arr[3] = 80;
        arr[4] = 90;

        // Displaying the initial Stack
        System.out.println("The initial Stack is: ");
        for (Integer str : arr)
            System.out.println(str);

        // Copying
        stack.copyInto(arr);

        // The final Stack
        System.out.println("The final Stack is: ");
        for (Integer str : arr)
            System.out.println(str);
    }
}
```

**Output:**

```
Stack: [10, 20, 30, 40, 50]
The initial Stack is: 
50
60
70
80
90
null
The final Stack is: 
10
20
30
40
50
null

```