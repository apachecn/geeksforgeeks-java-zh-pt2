# Java 中 StringCharacterIterator()方法示例

> 原文:[https://www . geeksforgeeks . org/string characteriater-current-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-current-method-in-java-with-examples/)

**电流()**方法**T3。Java 中的 stringcharacteriaterter 类**用来获取这个 stringcharacteriaterter 要读取的当前字符。此方法返回当前字符。

**语法:**

```
public char current()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回该字符串特征符要读取的当前字符。

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

        StringCharacterIterator stringCharacterIterator
            = new StringCharacterIterator(
                "GeeksForGeeks");

        System.out.println("Current character: "
                           + stringCharacterIterator
                                 .current());
    }
}
```

**输出:**

```
Current character: G

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # current–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#current--)