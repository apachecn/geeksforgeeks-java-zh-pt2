# Java 中的 stringcharacteriaterter getIndex()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-getindex-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-getindex-method-in-java-with-examples/)

**getIndex()** 法**法[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的 stringcharacteriaterter 类**用来获取这个 stringcharacteriaterter 要读取的当前索引。此方法返回该索引号。

**语法:**

```java
public int getIndex()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个 StringCharacterIterator 要读取的索引号。

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

        StringCharacterIterator stringCharacterIterator
            = new StringCharacterIterator(
                "GeeksForGeeks");

        System.out.println("Current character: "
                           + stringCharacterIterator
                                 .current());

        System.out.println("Current Index: "
                           + stringCharacterIterator
                                 .getIndex());
    }
}
```

**输出:**

```java
Current character: G
Current Index: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # GetIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#getIndex--)