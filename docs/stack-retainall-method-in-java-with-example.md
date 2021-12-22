# 用示例

在 Java 中堆叠 retainAll()方法

> 原文:[https://www . geesforgeks . org/stack-retain all-method-in-Java-with-example/](https://www.geeksforgeeks.org/stack-retainall-method-in-java-with-example/)

**java.util.Stack** 类的**retainnal()**方法用于从该堆栈中保留指定集合中包含的所有元素。

**语法:**

```
public boolean retainAll(Collection c)
```

**参数:**该方法将**集合 c** 作为参数，包含要从该堆栈中保留的元素。

**返回值:**如果调用导致堆栈发生变化，该方法返回**真**。

**异常:**如果此堆栈包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则此方法将引发**空指针异常**。

以下是说明*retainal()*方法的例子。

**例 1:**

```
// Java program to demonstrate
// retainAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of Stack<Integer>
            Stack<Integer>
                stack1 = new Stack<Integer>();

            // Populating stack1
            stack1.add(1);
            stack1.add(2);
            stack1.add(3);
            stack1.add(4);
            stack1.add(5);

            // print stack1
            System.out.println("Stack before "
                               + "retainAll() operation : "
                               + stack1);

            // Creating another object of  Stack<Integer>
            Stack<Integer>
                stack2 = new Stack<Integer>();
            stack2.add(1);
            stack2.add(2);
            stack2.add(3);

            // print stack2
            System.out.println("Collection Elements"
                               + " to be retained : "
                               + stack2);

            // Removing elements from stack
            // specified in stack2
            // using retainAll() method
            stack1.retainAll(stack2);

            // print stack1
            System.out.println("Stack after "
                               + "retainAll() operation : "
                               + stack1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Stack before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retained : [1, 2, 3]
Stack after retainAll() operation : [1, 2, 3]

```

**示例 2:** 适用于*空指针异常*

```
// Java program to demonstrate
// retainAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of Stack<Integer>
            Stack<Integer>
                stack1 = new Stack<Integer>();

            // Populating stack1
            stack1.add(1);
            stack1.add(2);
            stack1.add(3);
            stack1.add(4);
            stack1.add(5);

            // print stack1
            System.out.println("Stack before "
                               + "retainAll() operation : "
                               + stack1);

            // Creating another object of  Stack<Integer>
            Stack<Integer>
                stack2 = null;

            // print stack2
            System.out.println("Collection Elements"
                               + " to be retained : "
                               + stack2);

            System.out.println("\nTrying to pass "
                               + "null as a specified element\n");

            // Removing elements from stack
            // specified in stack2
            // using retainAll() method
            stack1.retainAll(stack2);

            // print stack1
            System.out.println("Stack after "
                               + "retainAll() operation : "
                               + stack1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Stack before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retained : null

Trying to pass null as a specified element

Exception thrown : java.lang.NullPointerException

```