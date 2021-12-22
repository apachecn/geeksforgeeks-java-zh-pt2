# Java 中的模式 toString()方法，示例

> 原文:[https://www . geesforgeks . org/pattern-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-tostring-method-in-java-with-examples/)

**toString()** 一个**模式**类的方法，用于返回这个模式的字符串表示。这将返回编译该模式的正则表达式。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容作为参数。

**返回值:**这个方法返回这个模式的字符串表示。

下面的程序说明了 toString()方法:

**程序 1:**

```java
// Java program to demonstrate
// Pattern.toString() method

import java.util.regex.*;
public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "geeks";

        // create a Pattern using REGEX
        Pattern pattern = Pattern.compile(REGEX);

        // print pattern
        System.out.println("Pattern:" + pattern);
    }
}
```

**输出:**

```java
Pattern:geeks

```

**程序二:**

```java
// Java program to demonstrate
// Pattern.toString() method

import java.util.regex.*;
public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "[* & # $ !]+\\S";

        // create a Pattern using REGEX
        Pattern pattern = Pattern.compile(REGEX);

        // print pattern
        System.out.println("Pattern:" + pattern);
    }
}
```

**输出:**

```java
Pattern:[* & # $ !]+\S

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#toString())