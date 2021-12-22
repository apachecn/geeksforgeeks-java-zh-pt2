# Java 中 StringCharacterIterator()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-Java 中的第一种方法-示例/](https://www.geeksforgeeks.org/stringcharacteriterator-first-method-in-java-with-examples/)

**先()**法 **[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的 stringcharacteriaterter 类**用来获取这个 stringcharacteriaterter 开头的字符。此方法使用 getBeginIndex()将迭代器的位置设置为第一个字符，然后返回该字符。

**语法:**

```java
public char first()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法使用 getBeginIndex()，将迭代器的位置设置为第一个字符，然后返回该字符。

**异常:**这个方法不抛出任何异常。

**程序:**

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class StringCharacterIteratorDemo {
    public static void main(String[] args)
    {

        StringCharacterIterator
            stringCharacterIterator
            = new StringCharacterIterator(
                "GeeksForGeeks");

        System.out.println("First character: "
                           + stringCharacterIterator
                                 .first());
    }
}
```

**输出:**

```java
First character: G

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # first–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#first--)