# Java 中模式匹配(字符串、字符序列)方法，示例

> 原文:[https://www . geesforgeks . org/pattern-matchesstring-charsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-matchesstring-charsequence-method-in-java-with-examples/)

Java 中**模式**类的**匹配(String，CharSequence)** 方法用于回答输入的正则表达式是否匹配。为此，我们编译给定的正则表达式，并尝试匹配给定的输入，其中正则表达式和输入都作为参数传递给方法。如果一个模式要被多次使用，那么编译一次并重用它将比每次调用这个方法更有效。

**语法:**

```java
public static boolean matches(String regex, CharSequence input)

```

**参数:**该方法接受两个参数:

*   **正则表达式**:此参数代表要编译的表达式。
*   **输入**:需要匹配的字符序列。

**返回值:**这个方法返回一个布尔值，回答输入的正则表达式是否匹配。

以下程序说明了匹配(字符串、字符序列)方法:

**程序 1:**

```java
// Java program to demonstrate
// Pattern.matches(String, CharSequence) method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "(.*)(ee)(.*)?";

        // create the string
        // in which you want to search
        String actualString
            = "geeksforgeeks";

        // use matches method to check the match
        boolean matcher = Pattern.matches(REGEX, actualString);

        // print values if match found
        if (matcher) {
            System.out.println("match found for Regex.");
        }
        else {
            System.out.println("No match found for Regex.");
        }
    }
}
```

**Output:**

```java
match found for Regex.

```

**程序 2:**

```java
// Java program to demonstrate
// Pattern.matches(String, CharSequence) method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "(.*)(welcome)(.*)?";

        // create the string
        // in which you want to search
        String actualString
            = "The indian team wins worldcup";

        // use matches() method to check the match
        boolean matcher = Pattern.matches(REGEX, actualString);

        // print values if match found
        if (matcher) {
            System.out.println("match found for Regex.");
        }
        else {
            System.out.println("No match found for Regex.");
        }
    }
}
```

**Output:**

```java
No match found for Regex.

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # matches(Java . lang . string，java.lang.CharSequence)](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#matches(java.lang.String, java.lang.CharSequence))