# Java 中的 NumberFormat parseObject()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-parseobject-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-parseobject-method-in-java-with-examples/)

**parseObject()** 方法是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，该方法从字符串中解析文本以生成数字。该函数试图从给定的索引开始解析文本。当解析发生时，给定的索引被设置为最后使用的字符，如果解析失败，给定的索引不变，错误索引被设置为发生错误的索引。

**语法:**

> 公共最终对象 parseObject(字符串源，ParsePosition pos)

**参数**:该功能接受两个参数，描述如下:

*   **来源**:指定要解析的字符串
*   **pos** :按照描述用索引和错误索引信息指定 ParsePosition 对象

**返回值**:函数返回一个布尔值，如果数字可以解析为整数，则返回 true，否则返回 false。

**异常**:如果源或位置被初始化为空，函数抛出**空指针异常**。

下面是上述功能的实现:

**程序 1** :

```
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.text.ParsePosition;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get the instance
        NumberFormat nF
            = NumberFormat.getNumberInstance();

        // Prints the parsed number or NULL
        System.out.println(nF
                               .parseObject("456",
                                            new ParsePosition(0)));
    }
}
```

**输出:**

```
456

```

**程序二:**

```
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;
import java.text.ParsePosition;

public class Main {
    public static void main(String[] args)
        throws Exception
    {
        try {
            // Get the instance
            NumberFormat nF
                = NumberFormat.getNumberInstance();

            // Prints the parsed number or NULL
            System.out.println(
                nF
                    .parseObject(null,
                                 new ParsePosition(0)));
        }
        catch (Exception e) {
            System.out.println("Exception: "
                               + e);
        }
    }
}
```

**输出:**

```
Exception: java.lang.NullPointerException

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/number format . html # parseObject(Java . lang . string，java.text.ParsePosition)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#parseObject(java.lang.String, java.text.ParsePosition))