# Java 中的堆栈搜索()方法

> 原文:[https://www.geeksforgeeks.org/stack-search-method-in-java/](https://www.geeksforgeeks.org/stack-search-method-in-java/)

java 中的 Java . util . stack . search(*Object element*)方法是用来在堆栈中搜索一个元素，得到它与顶部的距离。此方法从 1 开始计数，而不是从 0 开始计数。堆栈顶部的元素被认为位于位置 1。如果存在多个元素，则返回最接近顶部的元素的索引。如果成功找到元素，方法返回其位置，如果元素不存在，方法返回-1。

**语法:**

```
STACK.search(*element*)
```

**参数:**该方法接受一个参数*元素*，该元素是指堆栈中需要搜索的元素。

**返回值:**该方法返回元素的*位置*，如果在堆栈中成功找到(以计数为基数 1)，则返回-1。

以下程序说明了 java.util.Stack.search()方法的工作:
**程序 1:**

```
// Java code to demonstrate search() method
import java.util.*;

public class Stack_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Stack
        Stack<String> STACK = new Stack<String>();

        // Stacking strings
        STACK.push("Geeks");
        STACK.push("4");
        STACK.push("Geeks");
        STACK.push("Welcomes");
        STACK.push("You");

        // Displaying the Stack
        System.out.println("The stack is: " + STACK);

        // Checking for the element "4"
        System.out.println("Does the stack contains '4'? "
                                     + STACK.search("4"));
        // Checking for the element "Hello"
        System.out.println("Does the stack contains 'Hello'? "
                                     + STACK.search("Hello"));

        // Checking for the element "Geeks"
        System.out.println("Does the stack contains 'Geeks'? "
                                     + STACK.search("Geeks"));
    }
}
```

**Output:**

```
The stack is: [Geeks, 4, Geeks, Welcomes, You]
Does the stack contains '4'? 4
Does the stack contains 'Hello'? -1
Does the stack contains 'Geeks'? 3

```

**程序 2:**

```
// Java code to demonstrate search() method
import java.util.*;

public class Stack_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Stack
        Stack<Integer> STACK = new Stack<Integer>();

        // Stacking int values
        STACK.push(8);
        STACK.push(5);
        STACK.push(9);
        STACK.push(2);
        STACK.push(4);

        // Displaying the Stack
        System.out.println("The stack is: " + STACK);

        // Checking for the element 9
        System.out.println("Does the stack contains '9'? "
                                       + STACK.search(9));
        // Checking for the element 10
        System.out.println("Does the stack contains '10'? "
                                       + STACK.search(10));

        // Checking for the element 11
        System.out.println("Does the stack contains '11'? "
                                       + STACK.search(11));
    }
}
```

**Output:**

```
The stack is: [8, 5, 9, 2, 4]
Does the stack contains '9'? 3
Does the stack contains '10'? -1
Does the stack contains '11'? -1

```