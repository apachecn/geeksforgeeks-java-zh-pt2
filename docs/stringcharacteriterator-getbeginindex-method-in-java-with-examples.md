# Java 中的 stringcharacteriaterter getBeginIndex()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-getbeginindex-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-getbeginindex-method-in-java-with-examples/)

**getBeginIndex()** 法的**法的[法的](https://www.geeksforgeeks.org/tag/java-text-package/)法。Java 中的 stringcharacterTerter 类**用于获取这个 stringcharacterTerter 要读取的开头的索引。此方法返回该索引号。

**语法:**

```
public int getBeginIndex()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个 StringCharacterIterator 要读取的开头的索引。

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

        System.out.println("Current BeginIndex: "
                           + stringCharacterIterator
                                 .getBeginIndex());
    }
}
```

**输出:**

```
Current BeginIndex: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # getBeginIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#getBeginIndex--)