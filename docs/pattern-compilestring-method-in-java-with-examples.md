# Java 中的模式编译(字符串)方法，示例

> 原文:[https://www . geesforgeks . org/pattern-compilesting-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-compilestring-method-in-java-with-examples/)

Java 中**模式**类的**编译(字符串)**方法用于从作为参数传递给方法的正则表达式创建模式。每当需要多次将文本与正则表达式模式进行匹配时，请使用 Pattern.compile()方法创建一个模式实例。
**语法:**

```java
public static Pattern compile(String regex)
```

**参数:**这个方法接受一个单参数**正则表达式**，它代表编译成模式的给定正则表达式。
**返回值:**该方法返回从传递给该方法的正则表达式编译的模式作为参数。
**异常:**该方法抛出以下异常:

*   **patternsyntaxception:**如果表达式的语法无效，将引发此异常。

以下程序说明编译(字符串)方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Pattern.compile() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = ".*www.*";

        // creare the string
        // in which you want to search
        String actualString
            = "www.geeksforgeeks.org";

        // compile the regex to create pattern
        // using compile() method
        Pattern pattern = Pattern.compile(REGEX);

        // get a matcher object from pattern
        Matcher matcher = pattern.matcher(actualString);

        // check whether Regex string is
        // found in actualString or not
        boolean matches = matcher.matches();

        System.out.println("actualString "
                           + "contains REGEX = "
                           + matches);
    }
}
```

**Output:** 

```java
actualString contains REGEX = true
```