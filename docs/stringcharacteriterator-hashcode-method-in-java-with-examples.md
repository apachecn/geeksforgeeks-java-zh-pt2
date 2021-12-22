# Java 中 StringCharacterIterator hashCode()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-hashcode-method-in-java-with-examples/)

**[的 **hashCode()** 方法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的 stringcharacteriaterter 类**用来获取这个 stringcharacteriaterter 的 hashCode 值。这个方法返回一个代表 hashCode 值的整数。

**语法:**

```java
public int hashCode()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个 int，它是这个 StringCharacterIterator 的 hashCode 值。

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

        String text = "GeeksForGeeks";

        StringCharacterIterator
            stringCharacterIterator
            = new StringCharacterIterator(text);

        System.out.println("Current Text: "
                           + text);

        System.out.println("HashCode value: "
                           + stringCharacterIterator
                                 .hashCode());
    }
}
```

**输出:**

```java
Current Text: GeeksForGeeks
HashCode value: -1054991464

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#hashCode--)