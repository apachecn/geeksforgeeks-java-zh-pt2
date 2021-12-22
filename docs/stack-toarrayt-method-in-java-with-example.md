# 用示例

将 Java 中的 Array(T[])方法堆叠起来

> 原文:[https://www . geesforgeks . org/stack-to arrayt-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-toarrayt-method-in-java-with-example/)

Java 中[栈类](https://www.geeksforgeeks.org/java-util-Stack-class-java/)的 **toArray(T[])** 方法方法用于形成与栈相同元素的数组。它返回一个数组，包含这个堆栈中所有元素的正确顺序**；**返回数组的运行时类型是指定数组的运行时类型。如果堆栈适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此堆栈的大小来分配新数组。
如果堆栈适合指定的数组，且有剩余空间(即数组中的元素比堆栈多)，数组中紧接堆栈末尾的元素将被设置为空。(只有当调用方知道堆栈不包含任何空元素时，这才有助于确定堆栈的长度。)

**语法:**

```java
Object[] arr1 = Stack.toArray(arr[])
```

**参数:**该方法接受一个参数 **arr[]** ，如果堆栈足够大，则该参数是堆栈元素要存储到的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该方法返回一个包含类似于堆栈元素的数组。

**异常:**该方法可能会引发两种类型的异常:

*   **arraystorexception**:当提到的数组类型不同，无法与栈中提到的元素进行比较时。
*   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

下面的程序说明了 Stack.toArray(arr[])方法的工作原理。

**程序 1:** 当数组具有堆栈大小时

```java
// Java code to illustrate toArray(arr[])

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
        stack.add("For");
        stack.add("Geeks");

        // Displaying the Stack
        System.out.println("The Stack: " + stack);

        // Creating the array and using toArray()
        String[] arr = new String[5];
        arr = stack.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The Stack: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks

```

**程序 2:** 当数组小于堆栈大小时

```java
// Java code to illustrate toArray(arr[])

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
        stack.add("For");
        stack.add("Geeks");

        // Displaying the Stack
        System.out.println("The Stack: " + stack);

        // Creating the array and using toArray()
        String[] arr = new String[1];
        arr = stack.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The Stack: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks

```

**程序 3:** 当数组大于堆栈大小时

```java
// Java code to illustrate toArray(arr[])

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
        stack.add("For");
        stack.add("Geeks");

        // Displaying the Stack
        System.out.println("The Stack: " + stack);

        // Creating the array and using toArray()
        String[] arr = new String[10];
        arr = stack.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The Stack: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks
null
null
null
null
null

```

**程序 4:** 演示空指针异常

```java
// Java code to illustrate toArray(arr[])

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
        stack.add("For");
        stack.add("Geeks");

        // Displaying the Stack
        System.out.println("The Stack: " + stack);

        try {
            // Creating the array
            String[] arr = null;
            // using toArray()
            // Since arr is null
            // Hence exception will be thrown
            arr = stack.toArray(arr);

            // Displaying arr
            System.out.println("The arr[] is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
The Stack: [Welcome, To, Geeks, For, Geeks]
Exception: java.lang.NullPointerException

```