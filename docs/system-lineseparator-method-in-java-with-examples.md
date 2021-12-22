# Java 中 System.lineSeparator()方法示例

> 原文:[https://www . geesforgeks . org/system-line separator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/system-lineseparator-method-in-java-with-examples/)

lineSeparator()是 Java 中的内置方法，它返回依赖于系统的行分隔符字符串。它总是返回相同的值——系统属性行的初始值。

**语法:**

```
public static String lineSeparator()
```

**参数:**该方法不取任何参数。

**返回值:**在任何 UNIX 系统中，都会返回“\n”或正整数；在 Windows 系统上，它返回“\r\n”或正整数。

**异常:**如果字符串为空，则抛出*空指针异常*

下面的程序说明了 System.lineSeparator()方法:

**程序 1:** 说明静态弦线分离器()方法的工作原理。

```
// Java program to demonstrate working
// of static String lineSeparator() method
import java.io.IOException;
import java.lang.*;
import java.nio.channels.Channel;
public class LineSeparatorExample {

    public static void main(String[] args)
    {
        String s = System.lineSeparator();

        for (char c : s.toCharArray()) {
            System.out.println((int)c);
        }
    }
}
```

**输出:**

```
10

```

**注意:**这里返回 10。这里 10 是行分隔符。

**程序 2:** 说明一个整数值的静态字符串行分离器()方法的工作原理。

```
// Java program to demonstrate working
// of static String lineSeparator() method
import java.io.IOException;
import java.lang.*;
import java.nio.channels.Channel;
class SystemDemo {
    public static void main(String args[])
        throws NullPointerException,
               IOException
    {
        Integer x = 636;
        System.out.println(System.lineSeparator());
    }
}
```

**输出:**

```
\r\n

```

**注意:**这里返回“\r\n”，因为是微软 Windows 系统。

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/system . html # line separator()](https://docs.oracle.com/javase/7/docs/api/java/lang/System.html#lineSeparator())