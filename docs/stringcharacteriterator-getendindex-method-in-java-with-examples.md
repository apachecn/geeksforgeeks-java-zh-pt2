# Java 中的 stringcharacteriaterter getEndIndex()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-getendindex-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-getendindex-method-in-java-with-examples/)

**getEndIndex()**的**法的[法。Java 中的 stringcharacteriaterter 类](https://www.geeksforgeeks.org/tag/java-text-package/)**用于获取这个 stringcharacteriaterter 要读取的结尾的索引。此方法返回该索引号。

**语法:**

```
public int getEndIndex()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回该字符串特征符要读取的结尾索引。

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

        System.out.println("Current EndingIndex: "
                           + stringCharacterIterator
                                 .getEndIndex());
    }
}
```

**输出:**

```
Current EndingIndex: 13

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # getEndIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#getEndIndex--)