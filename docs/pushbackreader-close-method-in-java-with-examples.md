# Java 中的推读关闭()方法，示例

> 原文:[https://www . geesforgeks . org/puback reader-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackreader-close-method-in-java-with-examples/)

Java 中 **[推回阅读器](https://www.geeksforgeeks.org/java-io-pushbackreader-class-java/)** 类的 **close()** 方法用于关闭流并释放流中繁忙的资源(如果有)。该方法有以下结果:

*   If the stream is open, close the stream to release resources.
*   If the stream has been closed, it has no effect.
*   If the stream performs any reading or other similar operations, it will throw IOException when it is closed.

**语法:**

```
public void close()
```

**参数:**该方法不接受任何参数

**返回值:**此方法不返回值。

**异常:**如果输入输出时出现错误，该方法抛出**异常**。

下面的方法说明了 close()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PushbackReader close() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            String s = "GeeksForGeeks";

            // Initializing a StringReader and PushbackReader
            StringReader stringReader
                = new StringReader(s);
            PushbackReader pushbackReader
                = new PushbackReader(stringReader);

            System.out.println("Is stream ready: "
                               + pushbackReader.ready());

            // Close the stream using close()
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
Is stream ready: true
Stream Closed.

```

**程序二:**

```
// Java program to demonstrate
// PushbackReader close() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            // Initializing a StringReader and PushbackReader
            String s = "GFG";

            StringReader stringReader
                = new StringReader(s);
            PushbackReader pushbackReader
                = new PushbackReader(stringReader);

            System.out.println("Is stream ready: "
                               + pushbackReader.ready());

            // Close the stream using close()
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
Is stream ready: true
Stream Closed.

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/puback reader . html # close–](https://docs.oracle.com/javase/9/docs/api/java/io/PushbackReader.html#close--)