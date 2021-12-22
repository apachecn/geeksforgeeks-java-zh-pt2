# Java 中 StringTokenizer hasMoreTokens()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringtokenizer-hasmoretokens-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringtokenizer-hasmoretokens-method-in-java-with-examples/)

**StringTokenizer 类**的**hasmoretkens()**方法检查该 StringTokenizer 是否还有可用的令牌。

**语法:**

```java
public boolean hasMoreTokens()
```

**参数:**该方法不取任何参数。

**返回值:**如果在当前位置之后的字符串中发现至少还有一个令牌可用，则该方法返回布尔值 True，否则返回 false。

下面的程序说明了 StringTokenizer 的 hasMoreTokens()方法的工作:
**示例 1:**

```java
// Java code to illustrate hasMoreTokens() method

import java.util.*;

public class StringTokenizer_Demo {
    public static void main(String args[])
    {
        // Creating a StringTokenizer
        StringTokenizer str_arr
            = new StringTokenizer(
                "Lets practice at GeeksforGeeks");

        // Counting the tokens
        System.out.println("The number of Tokens are: "
                           + str_arr.countTokens());

        // Checking for any tokens
        System.out.println(str_arr.hasMoreTokens());

        // Checking and displaying the Tokens
        while (str_arr.hasMoreTokens()) {
            System.out.println("The Next token: "
                               + str_arr.nextToken());
        }
    }
}
```

**Output:**

```java
The number of Tokens are: 4
true
The Next token: Lets
The Next token: practice
The Next token: at
The Next token: GeeksforGeeks

```

**例 2:**

```java
// Java code to illustrate hasMoreTokens() method

import java.util.*;

public class StringTokenizer_Demo {
    public static void main(String args[])
    {
        // Creating a StringTokenizer
        StringTokenizer str_arr
            = new StringTokenizer("");

        // Counting the tokens
        System.out.println("The number of Tokens are: "
                           + str_arr.countTokens());

        // Checking for any tokens
        System.out.println(str_arr.hasMoreTokens());
    }
}
```

**Output:**

```java
The number of Tokens are: 0
false

```