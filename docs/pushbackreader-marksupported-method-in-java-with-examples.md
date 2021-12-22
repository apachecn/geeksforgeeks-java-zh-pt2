# 推回阅读器标记支持的()方法，带示例

> 原文:[https://www . geesforgeks . org/puback reader-marksupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackreader-marksupported-method-in-java-with-examples/)

Java 中 **[推回阅读器类](https://www.geeksforgeeks.org/java-io-pushbackreader-class-java/)** 的 **markSupported()** 方法，用来检查这个推回阅读器是否支持 mark()操作。它返回一个布尔值，该值表示读取器是否被标记为受支持。

**语法:**

```
public boolean markSupported()
```

**参数:**该方法不接受任何参数

**返回值:**这个方法返回一个**布尔值**，这个值告诉这个推读器是否支持 mark()操作。如果它是 markSupported，则返回 true。否则返回假。

下面的方法说明了 markSupported()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PushbackReader markSupported() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            // Initializing a StringReader
            // and PushbackReader
            String s = "GeeksForGeeks";

            StringReader stringReader
                = new StringReader(s);
            PushbackReader pushbackReader
                = new PushbackReader(stringReader);

            // check if the mark() method
            // is supported or not
            System.out.println("Is mark() supported:"
                               + pushbackReader.markSupported());

            // Close the stream using markSupported()
            pushbackReader.close();
            System.out.println("Stream Closed.");
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Is mark() supported:false
Stream Closed.

```

**程序二:**

```
// Java program to demonstrate
// PushbackReader markSupported() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            // Initializing a StringReader
            // and PushbackReader
            String s = "GFG";

            StringReader stringReader
                = new StringReader(s);
            PushbackReader pushbackReader
                = new PushbackReader(stringReader);

            // check if the mark() method
            // is supported or not
            System.out.println("Is mark() supported:"
                               + pushbackReader.markSupported());

            // Close the stream
            pushbackReader.close();
            System.out.println("Stream Closed.");
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Is mark() supported:false
Stream Closed.

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/puback reader . html # markSupported–](https://docs.oracle.com/javase/9/docs/api/java/io/PushbackReader.html#markSupported--)