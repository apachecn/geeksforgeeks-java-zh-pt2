# Java 中的模式标志()方法，示例

> 原文:[https://www . geesforgeks . org/pattern-flags-in-Java-method-with-examples/](https://www.geeksforgeeks.org/pattern-flags-method-in-java-with-examples/)

Java 中**模式**类的 **flags()** 方法用于返回模式的匹配标志。匹配标志是一个位掩码，可以包括不区分大小写、多行、多行、UNICODE_CASE、CANON_EQ、UNIX_LINES、LITERAL、UNICODE_CHARACTER_CLASS 和注释标志。

**语法:**

```java
public int flags()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回模式的匹配标志。

下面的程序说明了 flags()方法:

**程序 1:**

```java
// Java program to demonstrate
// Pattern.flags() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "(.*)(for)(.*)?";

        // create the string
        // in which you want to search
        String actualString
            = "code of Machine";

        // compile the regex to create pattern
        // using compile() method
        Pattern pattern = Pattern.compile(REGEX, 
                         Pattern.CASE_INSENSITIVE);

        // find the flag of pattern
        int flag = pattern.flags();

        System.out.println("Pattern's match flag = "
                           + flag);
    }
}
```

**Output:**

```java
Pattern's match flag = 2

```

**程序 2:**

```java
// Java program to demonstrate
// Pattern.compile method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a REGEX String
        String REGEX = "(.*)(ee)(.*)?";

        // create the string
        // in which you want to search
        String actualString
            = "geeks";

        // compile the regex to create pattern
        // using compile() method
        Pattern pattern = Pattern.compile(REGEX, 
                                 Pattern.MULTILINE);

        // find the flag of pattern
        int flag = pattern.flags();

        System.out.println("Pattern's match flag = "
                           + flag);
    }
}
```

**Output:**

```java
Pattern's match flag = 8

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # flags()](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#flags())