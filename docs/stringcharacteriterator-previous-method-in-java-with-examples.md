# Java 中 StringCharacterIterator previous()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-previous-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-previous-method-in-java-with-examples/)

**前朝()**法 **[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的 stringcharacterTerter 类**用来获取这个 stringcharacterTerter 要读取的前一个字符。这个方法将迭代器向后递减一个索引，并返回前一个字符。

**语法:**

```java
public char previous()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回该字符串特征符要读取的前一个字符。

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

        stringCharacterIterator.next();

        System.out.println("Current character: "
                           + stringCharacterIterator
                                 .current());

        System.out.println("Previous character: "
                           + stringCharacterIterator
                                 .previous());
    }
}
```

**输出:**

```java
Current character: e
Previous character: G

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # previous–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#previous--)