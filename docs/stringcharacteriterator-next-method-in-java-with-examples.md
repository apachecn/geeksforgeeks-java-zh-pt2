# Java 中 StringCharacterIterator()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacteriaterator-next-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-next-method-in-java-with-examples/)

**接下来()**法**法[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的 stringcharacteriaterter 类**用于获取该 stringcharacteriaterter 要读取的下一个字符。这个方法将迭代器向前递减一个索引，并返回下一个字符。

**语法:**

```
public char next()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回该字符串特征符要读取的下一个字符。

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

        System.out.println("Next character: "
                           + stringCharacterIterator
                                 .next());
    }
}
```

**输出:**

```
Current character: G
Next character: e

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # next–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#next--)