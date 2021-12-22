# Java 中的 StringTokenizer countTokens()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringtokenizer-count token-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringtokenizer-counttokens-method-in-java-with-examples/)

**StringTokenizer 类**的**count token()**方法计算在该方法生成任何进一步的异常之前，该标记器的 **nextToken** 方法可以被调用的次数。
**注意:**过程中当前位置不提前。

**语法:**

```
public int countTokens()
```

**参数:**该方法不取任何参数。

**返回值:**该方法用于使用当前分隔符集返回字符串中剩余的标记数。

下面的程序说明了 StringTokenizer 的 countTokens()方法的工作:
**示例 1:**

```
// Java code to illustrate countTokens() method

import java.util.*;

public class StringTokenizer_Demo1 {
    public static void main(String args[])
    {

        // Creating a StringTokenizer
        StringTokenizer str_arr
            = new StringTokenizer(
                "Lets practice at GeeksforGeeks");

        // Counting the tokens
        int count = str_arr.countTokens();
        System.out.println("Total number of Tokens: "
                           + count);

        // Print the tokens
        for (int i = 0; i < count; i++)
            System.out.println("token at [" + i + "] : "
                               + str_arr.nextToken());
    }
}
```

**Output:**

```
Total number of Tokens: 4
token at [0] : Lets
token at [1] : practice
token at [2] : at
token at [3] : GeeksforGeeks

```

**例 2:**

```
// Java code to illustrate countTokens() method

import java.util.*;

public class StringTokenizer_Demo2 {
    public static void main(String args[])
    {

        // Creating a StringTokenizer
        StringTokenizer str_arr
            = new StringTokenizer(
                "Welcome to GeeksforGeeks");

        // Counting the tokens
        int count = str_arr.countTokens();
        System.out.println("Total number of Tokens: "
                           + count);

        // Print the tokens
        for (int i = 0; i < count; i++)
            System.out.println("token at [" + i + "] : "
                               + str_arr.nextToken());
    }
}
```

**Output:**

```
Total number of Tokens: 3
token at [0] : Welcome
token at [1] : to
token at [2] : GeeksforGeeks

```