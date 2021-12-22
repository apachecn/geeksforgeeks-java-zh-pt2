# Java 中的模式分流()方法，示例

> 原文:[https://www . geesforgeks . org/pattern-splitassstream-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-splitasstream-method-in-java-with-examples/)

**splitassstream()**一个**模式**类的方法，用于从给定的输入序列中返回一个字符串流，作为参数传递给这个模式的匹配项。如果这个模式不匹配输入的任何子序列，那么结果流只有一个元素，即字符串形式的输入序列。

**语法:**

```java
public Stream<String> splitAsStream(CharSequence input)

```

**参数:**该方法接受单个参数**字符序列**，表示待拆分的字符序列。

**返回值:**该方法返回一个字符串流，该字符串流通过围绕该模式的匹配项分割输入来计算。

下面的程序说明了 splitAsStream()方法:

**程序 1:**

```java
// Java program to demonstrate
// Pattern.splitAsStream(CharSequence input) method

import java.util.regex.*;
import java.util.stream.*;
public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "geeks";

        // create the string
        // in which you want to search
        String actualString
            = "Welcome to geeks for geeks";

        // create a Pattern using REGEX
        Pattern pattern = Pattern.compile(REGEX);

        // split the text
        Stream<String> stream
            = pattern
                  .splitAsStream(actualString);

        // print array
        stream.forEach(System.out::println);
    }
}
```

**输出:**

```java
Welcome to 
 for

```

**程序二:**

```java
// Java program to demonstrate
// Pattern.splitAsStream(CharSequence input) method

import java.util.regex.*;
import java.util.stream.*;
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
        Pattern pattern = Pattern.compile(REGEX);

        // split the text
        Stream<String> stream
            = pattern
                  .splitAsStream(actualString);

        // print array
        stream.forEach(System.out::println);
    }
}
```

**输出:**

```java
aa
bb
cc
dd

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # splitassstream(Java . lang . charsequence)](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#splitAsStream(java.lang.CharSequence))