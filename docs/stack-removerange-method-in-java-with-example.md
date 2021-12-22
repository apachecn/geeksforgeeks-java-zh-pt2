# Java 中的堆栈移除范围()方法，示例

> 原文:[https://www . geesforgeks . org/stack-remove range-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-removerange-method-in-java-with-example/)

Java 中**栈**的 **removeRange()** 方法用于从栈对象中移除指定范围内的所有元素。它将任何后续元素向左移动。此调用通过(toIndex-fromIndex)元素来缩短堆栈，其中 toIndex 是结束索引，fromIndex 是开始索引，所有元素都将从该索引中移除。(如果 toIndex==fromIndex，此操作无效)
**语法:**

```
removeRange(int fromIndex, int toIndex)
```

**参数:**该方法取两个参数:

*   **fromIndex:** 要从中删除索引元素的起始索引。
*   **到索引:**在[从索引到索引]的范围内，所有元素都被删除。

**返回值:**此方法不返回值。它只移除指定范围内的所有元素。
**异常:**如果 fromIndex 或 toIndex 超出范围(fromIndex = size()或 toIndex > size()或 toIndex < fromIndex)
此方法将抛出*T6】indexout of boundsexception*以下示例说明了 Stack.removeRange()方法:
**示例 1** :演示 removeRange()方法的使用

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// working of removeRange() method

import java.util.*;

// extending the class to stackyastack since removeRange()
// is a protected method
public class GFG extends Stack<Integer> {

    public static void main(String[] args)
    {

        // create an empty  stack

        GFG stack = new GFG();

        // use add() method to add values in the stack
        stack.add(1);
        stack.add(2);
        stack.add(3);
        stack.add(12);
        stack.add(9);
        stack.add(13);

        // prints the stack before removing
        System.out.println("The stack before using removeRange:"
                           + stack);

        // removing range of 1st 2 elements
        stack.removeRange(0, 2);
        System.out.println("The stack after using removeRange:"
                           + stack);
    }
}
```

**Output:** 

```
The stack before using removeRange:[1, 2, 3, 12, 9, 13]
The stack after using removeRange:[3, 12, 9, 13]
```

**示例 2** :演示错误的程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the error in
// working of removeRange() method

import java.util.*;

// extending the class to stackyastack since removeRange()
// is a protected method
public class GFG extends Stack<Integer> {

    public static void main(String[] args)
    {

        // create an empty stack stack

        GFG stack = new GFG();

        // use add() method to add values in the stack
        stack.add(1);
        stack.add(2);
        stack.add(3);

        try {
            // error as 4 is out of range
            stack.removeRange(1, 4);

            System.out.println("The stack after using removeRange:"
                               + stack);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:** 

```
java.lang.ArrayIndexOutOfBoundsException
```