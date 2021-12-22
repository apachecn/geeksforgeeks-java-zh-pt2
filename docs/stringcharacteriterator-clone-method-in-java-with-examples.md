# Java 中 StringCharacterIterator 克隆()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-clone-method-in-java-with-examples/)

**克隆()**法的 **[法的](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的 stringcharacteriaterter 类**用来克隆这个 stringcharacteriaterter。这意味着此方法将创建另一个 stringcharacterterator 实例，其所有属性与此 stringcharacterterator 相同，并返回它。

**语法:**

```
public Object clone()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**对象**，它是这个字符串特征符的克隆。

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

        System.out.println("Current StringCharacterIterator: "
                           + stringCharacterIterator);

        System.out.println("Cloned StringCharacterIterator: "
                           + stringCharacterIterator.clone());
    }
}
```

**输出:**

```
Current StringCharacterIterator:
 java.text.StringCharacterIterator@c11e1b98
Cloned StringCharacterIterator:
 java.text.StringCharacterIterator@c11e1b98

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharactersterator . html # clone–](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#clone--)