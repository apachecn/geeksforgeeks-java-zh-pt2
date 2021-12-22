# Java 中的推读复位()方法，示例

> 原文:[https://www . geesforgeks . org/puback reader-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackreader-reset-method-in-java-with-examples/)

Java 中 **[推读类](https://www.geeksforgeeks.org/java-io-pushbackreader-class-java/)** 的**重置()**方法用于重置流。在推送阅读器的情况下，该方法总是引发异常，因为推送阅读器不支持该方法。

**语法:**

```java
public void reset()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**由于不支持 reset()方法，此方法总是引发 IOException。

下面的方法说明了 reset()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PushbackReader reset() method

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

            // reset the stream position
            pushbackReader.reset();

            // Close the stream using reset()
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
// PushbackReader reset() method

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

            // reset the stream position
            pushbackReader.reset();

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

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/puback reader . html # reset–](https://docs.oracle.com/javase/9/docs/api/java/io/PushbackReader.html#reset--)