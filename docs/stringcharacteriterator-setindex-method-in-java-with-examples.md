# Java 中 stringcharacteriaterter setIndex()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-set index-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-setindex-method-in-java-with-examples/)

**[的**设置索引()**方法。Java 中的 stringcharacterTerter 类](https://www.geeksforgeeks.org/tag/java-text-package/)**用来设置这个 stringcharacterTerter 要读取的当前索引。此方法将待设置的索引作为参数，并在该索引处设置该 StringCharacterIterator 的索引，然后返回该字符。

**语法:**

```
public char setIndex(int index)

```

**参数:**该方法以待设置的**指标**为参数，设置该字符串特征符的指标。

**返回值:**该方法返回该方法设置的索引处的字符。

**异常:**如果指定的索引不在有效范围(getBeginIndex()、getEndIndex()–1)内，此方法将引发 IllegalArgumentException。

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

        System.out.println("Current Index: "
                           + stringCharacterIterator
                                 .getIndex());

        int index = 5;

        System.out.println("Updated the index to: "
                           + index);

        System.out.println("Character at new current index: "
                           + stringCharacterIterator
                                 .setIndex(index));
    }
}
```

**输出:**

```
Current Index: 0
Updated the index to: 5
Character at new current index: F

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharacteriaterter . html # setIndex-int-](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#setIndex-int-)