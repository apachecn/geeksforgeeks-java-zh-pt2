# Java 中的 StringTokenizer nextElement()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringtokenizer-next element-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringtokenizer-nextelement-method-in-java-with-examples/)

**StringTokenizer 类**的 **nextElement()** 方法也用于从这个 StringTokenizer 中一个接一个地返回下一个令牌。它类似于 nextToken()方法，只是返回类型是 Object 而不是 String。

**语法:**

```java
public Object nextElement()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回字符串标记器行中的下一个标记。

下面的程序说明了 StringTokenizer 的 nextElement()方法的工作原理:

**例 1:**

```java
// Java code to illustrate nextElement() method

import java.util.*;

public class StringTokenizer_Demo {
    public static void main(String args[])
    {
        // Creating a StringTokenizer
        StringTokenizer str_arr
            = new StringTokenizer(
                "Lets practice at GeeksforGeeks");

        // Displaying the Tokens
        while (str_arr.hasMoreElements()) {
            System.out.println("The Next token: "
                               + str_arr.nextElement());
        }
    }
}
```

**Output:**

```java
The Next token: Lets
The Next token: practice
The Next token: at
The Next token: GeeksforGeeks

```

**例 2:**

```java
// Java code to illustrate nextElement() method

import java.util.*;

public class StringTokenizer_Demo {
    public static void main(String args[])
    {
        // Creating a StringTokenizer
        StringTokenizer str_arr
            = new StringTokenizer(
                "Welcome to GeeksforGeeks");

        // Displaying the Tokens
        while (str_arr.hasMoreElements()) {
            System.out.println("The Next token: "
                               + str_arr.nextElement());
        }
    }
}
```

**Output:**

```java
The Next token: Welcome
The Next token: to
The Next token: GeeksforGeeks

```