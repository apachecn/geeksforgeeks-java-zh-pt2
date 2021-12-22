# Java 中的 StringTokenizer nextToken()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringtokenizer-next token-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringtokenizer-nexttoken-method-in-java-with-examples/)

**StringTokenizer 类**的 **nextToken()** 方法用于从这个 StringTokenizer 中一个接一个地返回下一个令牌。

**语法:**

```
public String nextToken()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回字符串标记器行中的下一个标记。

下面的程序说明了 StringTokenizer 的 nextToken()方法的工作原理:

**例 1:**

```
// Java code to illustrate nextToken() method

import java.util.*;

public class StringTokenizer_Demo {
    public static void main(String args[])
    {
        // Creating a StringTokenizer
        StringTokenizer str_arr
            = new StringTokenizer(
                "Lets practice at GeeksforGeeks");

        // Displaying the Tokens
        while (str_arr.hasMoreTokens()) {
            System.out.println("The Next token: "
                               + str_arr.nextToken());
        }
    }
}
```

**Output:**

```
The Next token: Lets
The Next token: practice
The Next token: at
The Next token: GeeksforGeeks

```

**例 2:**

```
// Java code to illustrate nextToken() method

import java.util.*;

public class StringTokenizer_Demo {
    public static void main(String args[])
    {
        // Creating a StringTokenizer
        StringTokenizer str_arr
            = new StringTokenizer(
                "Welcome to GeeksforGeeks");

        // Displaying the Tokens
        while (str_arr.hasMoreTokens()) {
            System.out.println("The Next token: "
                               + str_arr.nextToken());
        }
    }
}
```

**Output:**

```
The Next token: Welcome
The Next token: to
The Next token: GeeksforGeeks

```