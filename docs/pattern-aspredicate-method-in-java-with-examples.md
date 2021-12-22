# Java 中的模式描述()方法，示例

> 原文:[https://www . geesforgeks . org/pattern-asprediate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-aspredicate-method-in-java-with-examples/)

用于创建可用于匹配字符串的谓词对象的**模式**类的 **asPredicate()** 方法。谓词是一个函数接口，因此可以用作 lambda 表达式或方法引用的赋值目标。

**语法:**

```java
public Predicate asPredicate()

```

**参数:**此方法不接受任何内容作为参数。

**返回值:**这个方法返回一个谓词，可以用来匹配字符串。

下面的程序说明了 toString()方法:

**程序 1:**

```java
// Java program to demonstrate
// Pattern.splitAsStream(CharSequence input) method

import java.util.regex.*;
import java.util.function.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "ee";

        // create the string
        // in which you want to search
        String actualString
            = "aaeebbeecceeddee";

        // create a Pattern using REGEX
        Pattern pattern
            = Pattern.compile(REGEX);

        // get Predicate Object
        Predicate<String> predicate
            = pattern.asPredicate();

        // check whether predicate match
        // with actualString
        boolean value = predicate
                            .test(actualString);

        // print result
        System.out.println("value matched: "
                           + value);
    }
}
```

**输出:**

```java
value matched: true

```

**程序二:**

```java
// Java program to demonstrate
// Pattern.splitAsStream(CharSequence input) method

import java.util.regex.*;
import java.util.function.*;
public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "org";

        // create the string
        // in which you want to search
        String actualString
            = "welcome geeks";

        // create a Pattern using REGEX
        Pattern pattern
            = Pattern.compile(REGEX);

        // get Predicate Object
        Predicate<String> predicate
            = pattern.asPredicate();

        // check whether predicate match
        // with actualString
        boolean value
            = predicate.test(actualString);

        // print result
        System.out.println("value matched: "
                           + value);
    }
}
```

**输出:**

```java
value matched: false

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # asprediate()](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#asPredicate())