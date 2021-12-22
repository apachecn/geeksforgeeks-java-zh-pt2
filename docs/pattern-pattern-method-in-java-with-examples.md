# Java 中的 Pattern pattern()方法，带示例

> 原文:[https://www . geesforgeks . org/pattern-pattern-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-pattern-method-in-java-with-examples/)

Java 中**模式**类的**模式()**方法用于获取正则表达式，该表达式是为创建该模式而编译的。我们使用一个正则表达式来创建模式，这个方法用来获得相同的源表达式。

**语法:**

```
public String pattern()

```

**参数:**这个方法不接受任何东西作为参数。

**返回值:**这个方法返回模式的源正则表达式。

下面的程序说明了模式()方法:
**程序 1:**

```
// Java program to demonstrate
// Pattern.pattern() method

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

        // create pattern
        Pattern pattern1 = Pattern.compile(REGEX);

        // find the regular expressio of pattern
        String RegularExpression = pattern1.pattern();

        System.out.println("Pattern's RegularExpression = "
                           + RegularExpression);
    }
}
```

**Output:**

```
Pattern's RegularExpression = (.*)(for)(.*)?

```

**程序 2:**

```
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

        // create pattern
        Pattern pattern1 = Pattern.compile(REGEX);

        // find the regular expressio of pattern
        String RegularExpression = pattern1.pattern();

        System.out.println("Pattern's RegularExpression = "
                           + RegularExpression);
    }
}
```

**Output:**

```
Pattern's RegularExpression = (.*)(ee)(.*)?

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # pattern()](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#pattern())