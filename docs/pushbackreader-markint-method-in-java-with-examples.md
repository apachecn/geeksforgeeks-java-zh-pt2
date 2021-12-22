# Java 中的推读标记(int)方法，示例

> 原文:[https://www . geesforgeks . org/puback reader-markint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackreader-markint-method-in-java-with-examples/)

Java 中 **[推读器类](https://www.geeksforgeeks.org/java-io-pushbackreader-class-java/)** 的**标记()**方法用于标记推读器的当前位置。在推送阅读器的情况下，该方法总是引发异常，因为推送阅读器不支持该方法。

**语法:**

```java
public void mark(int readAheadLimit)
```

**参数:**该方法接受一个强制参数 **readAheadLimit** ，它是在保留标记的同时可以读取的字符数的限制。读取这么多字符后，尝试重置流可能会失败。

**返回值:**此方法不返回值。

**异常:**由于不支持 mark()方法，此方法总是引发 IOException。

下面的方法说明了 mark()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PushbackReader mark(int) method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            // Initializing a StringReader and PushbackReader
            String s = "GeeksForGeeks";

            StringReader stringReader
                = new StringReader(s);
            PushbackReader pushbackReader
                = new PushbackReader(stringReader);

            // mark the stream for
            // 5 characters using mark()
            pushbackReader.mark(5);

            // Close the stream using mark(int)
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

```java
java.io.IOException: mark/reset not supported

```

**程序二:**

```java
// Java program to demonstrate
// PushbackReader mark(int) method

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

            // mark the stream for
            // 1 characters using mark()
            pushbackReader.mark(1);

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

```java
java.io.IOException: mark/reset not supported

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/puback reader . html # mark-int-](https://docs.oracle.com/javase/9/docs/api/java/io/PushbackReader.html#mark-int-)