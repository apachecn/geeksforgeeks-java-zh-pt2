# Java 中的 StringCharacterIterator setText()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-settext-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-settext-method-in-java-with-examples/)

**[的 **setText()** 方法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的 stringcharacterTerter 类**用于设置该 stringcharacterTerter 要读取的当前文本。此方法将待设置的文本作为参数，并将该字符串的文本设置为该文本。

**语法:**

```
public void setText(String text)

```

**参数:**该方法将待设置的文本作为参数，设置该 StringCharacterIterator 的文本。

**返回值:**这个方法不返回任何东西。

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

        String text = "GeeksForGeeks";

        StringCharacterIterator
            stringCharacterIterator
            = new StringCharacterIterator(text);

        System.out.println("Current Text: "
                           + text);

        text = "Geeks for Geeks";

        stringCharacterIterator.setText(text);

        System.out.println("New text: "
                           + text);
    }
}
```

**输出:**

```
Current Text: GeeksForGeeks
New text: Geeks for Geeks

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # setText-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#setText-java.lang.String-)