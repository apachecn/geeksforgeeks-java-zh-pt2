# Java 中的模式编译(String，int)方法，示例

> 原文:[https://www . geesforgeks . org/pattern-compilestingint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-compilestringint-method-in-java-with-examples/)

**模式**类的**编译(String，int)** 方法用于借助标志从正则表达式创建模式，其中表达式和标志都作为参数传递给该方法。模式类包含一系列标志(int 常量)，这些标志有助于使模式匹配以某种方式运行。例如，标志名 CASE _ INSENSITIVE 用于在匹配时忽略文本的大小写。
**语法:**

```
public static Pattern compile(String regex, int flags)
```

**参数:**该方法接受两个参数:

*   **正则表达式**:这个参数代表编译成模式的给定正则表达式。
*   **标志**:此参数为表示 Match 标志的整数，位掩码可能包括 CASE _ INSENSITIVE、MULTILINE、DOTALL、UNICODE_CASE、CANON_EQ、UNIX_LINES、LITERAL、UNICODE_CHARACTER_CLASS 和 COMMENTS。

**返回值:**这个方法返回由传递的正则表达式和标志编译的模式。
**异常:**此方法抛出以下异常:

*   **patternsyntaxception:**如果表达式的语法无效，则会引发此异常。
*   **IllegalArgumentException:**如果在标志中设置了与定义的匹配标志不同的位值，则会引发此异常。

下面的程序说明编译(字符串，int)方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// Pattern.compile method

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

        // check whether Regex string is
        // found in actualString or not
        boolean matches = pattern
                              .matcher(actualString)
                              .matches();

        System.out.println("actualString "
                           + "contains REGEX = "
                           + matches);
    }
}
```

**Output:** 

```
actualString contains REGEX = false
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// Pattern.compile method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = ".*org.*";

        // create the string
        // in which you want to search
        String actualString
            = "geeksforgeeks.org";

        // compile the regex to create pattern
        // using compile() method
        Pattern pattern = Pattern.compile(REGEX,
                             Pattern.CASE_INSENSITIVE);

        // check whether Regex string is
        // found in actualString or not
        boolean matches = pattern
                              .matcher(actualString)
                              .matches();

        System.out.println("actualString "
                           + "contains REGEX = "
                           + matches);
    }
}
```

**Output:** 

```
actualString contains REGEX = true
```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # compile(Java . lang . string，int)](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#compile(java.lang.String, int))