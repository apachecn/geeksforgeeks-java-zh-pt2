# 用示例

在 Java 中堆叠 subList()方法

> 原文:[https://www . geesforgeks . org/stack-sublist-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-sublist-method-in-java-with-example/)

**Java.util.Stack** 类的 **subList()** 方法用于返回指定的 fromIndex(包含)和 toIndex(不包含)之间的堆栈部分的视图。(如果 fromIndex 和 toIndex 相等，则返回的堆栈为空。)

返回的堆栈由该堆栈支持，因此返回的堆栈中的非结构性变化反映在该堆栈中，反之亦然。返回的堆栈支持所有可选的堆栈操作。

**语法:**

```
public Stack subList(int fromIndex, int toIndex)
```

**参数:**该方法将以下参数作为参数。

*   **从索引–**子列表的低端点(含)
*   **到索引–**子列表的高端点(不包括)

**返回值:**该方法返回该堆栈内指定范围的**视图。**

**异常:**该方法抛出如下异常。

*   如果端点索引值超出范围(从索引大小开始)，则**indexout of BoundSexception–**
*   **如果端点索引出现故障，则出现 IllegalArgumentException–**(从索引>到索引)

下面是说明*子列表()*方法的例子。

**例 1:**

```
// Java program to demonstrate
// subList() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of Stack<Integer>
            Stack<String>
                stack = new Stack<String>();

            // Populating stack1
            stack.add("A");
            stack.add("B");
            stack.add("C");
            stack.add("D");
            stack.add("E");

            // print stack
            System.out.println("Original stack: "
                               + stack);

            // getting the subList
            // using subList() method
            List<String> stack2 = stack.subList(2, 4);

            // print the subList
            System.out.println("SubStack of stack: "
                               + stack2);
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Original stack: [A, B, C, D, E]
SubStack of stack: [C, D]

```

**示例 2:** 适用于*指数出界异常*

```
// Java program to demonstrate
// subList() method
// for IndexOutOfBoundsException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // Creating object of Stack<Integer>
            Stack<String>
                stack = new Stack<String>();

            // Populating stack1
            stack.add("A");
            stack.add("B");
            stack.add("C");
            stack.add("D");
            stack.add("E");

            // print stack
            System.out.println("Original stack: "
                               + stack);

            // getting the subList
            // using subList() method
            System.out.println("\nEnd index value is out of range");
            List<String> stack2 = stack.subList(2, 7);

            // print the subList
            System.out.println("SubStack of stack: "
                               + stack2);
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Original stack: [A, B, C, D, E]

End index value is out of range
java.lang.IndexOutOfBoundsException: toIndex = 7

```

**示例 3:** 适用于*非法文档异常*

```
// Java program to demonstrate
// subList() method
// for IllegalArgumentException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of Stack<Integer>
            Stack<String>
                stack = new Stack<String>();

            // Populating stack1
            stack.add("A");
            stack.add("B");
            stack.add("C");
            stack.add("D");
            stack.add("E");

            // print stack
            System.out.println("Original stack: "
                               + stack);

            // getting the subList
            // using subList() method
            System.out.println("\nEndpoint indices "
                               + "are out of order"
                               + " (fromIndex > toIndex)");
            List<String> stack2 = stack.subList(7, 2);

            // print the subList
            System.out.println("SubStack of stack: "
                               + stack2);
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Original stack: [A, B, C, D, E]

Endpoint indices are out of order (fromIndex > toIndex)
java.lang.IllegalArgumentException: fromIndex(7) > toIndex(2)

```