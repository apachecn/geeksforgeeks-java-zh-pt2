# Java 中 StringCharacterIterator last()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-Java 中的最后一种方法-示例/](https://www.geeksforgeeks.org/stringcharacteriterator-last-method-in-java-with-examples/)

**最后()**法**法[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的[string character 类](https://www.geeksforgeeks.org/tag/java-stringcharacteriterator/)** 用来获取这个 string character 末尾的字符。此方法使用 getEndIndex()将迭代器的位置设置为最后一个字符，然后返回该字符。

**语法:**

```
public char last()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法使用 getEndIndex()，将迭代器的位置设置为最后一个字符，然后返回那个**字符**。

**异常:**这个方法不抛出任何异常。

**程序:**

```
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

        System.out.println("Current character: "
                           + stringCharacterIterator
                                 .current());

        System.out.println("Last character: "
                           + stringCharacterIterator
                                 .last());
    }
}
```

**输出:**

```
Current character: G
Last character: s

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # last–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#last--)