# Java 中的推读 Reader ready()方法，示例

> 原文:[https://www . geesforgeks . org/puback reader-ready-in-Java-method-with-examples/](https://www.geeksforgeeks.org/pushbackreader-ready-method-in-java-with-examples/)

Java 中 **[推读器类](https://www.geeksforgeeks.org/java-io-pushbackreader-class-java/)** 的 **ready()** 方法用来检查这个推读器是否准备好被读取。它返回一个布尔值，表示读取器是否准备好了。

**语法:**

```java
public void ready()
```

**参数:**该方法不接受任何参数

**返回值:**该方法返回一个**布尔值**，该值告诉推读器是否准备好被读取。如果它准备好了，它就会变成真的。否则返回假。

**异常:**如果输入输出时出现错误，该方法抛出**异常**。

下面的方法说明了 ready()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PushbackReader ready() method

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

            // Check if the PushbackReader is
            // ready to be read using ready()
            System.out.println("Is PushbackReader ready "
                               + "to be read: "
                               + pushbackReader.ready());

            // Close the stream using ready()
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
Is PushbackReader ready to be read: true
Stream Closed.

```

**程序二:**

```java
// Java program to demonstrate
// PushbackReader ready() method

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

            // Check if the PushbackReader is
            // ready to be read using ready()
            System.out.println("Is PushbackReader ready "
                               + "to be read: "
                               + pushbackReader.ready());

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
Is PushbackReader ready to be read: true
Stream Closed.

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/puback reader . html # ready–](https://docs.oracle.com/javase/9/docs/api/java/io/PushbackReader.html#ready--)