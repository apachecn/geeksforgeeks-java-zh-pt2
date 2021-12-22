# Java 中的推读 Reader read()方法，示例

> 原文:[https://www . geesforgeks . org/puback reader-read-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackreader-read-method-in-java-with-examples/)

Java 中 **[推读类](https://www.geeksforgeeks.org/java-io-pushbackreader-class-java/)** 的 **read()** 方法用于从流中读取单个字符。这个方法阻塞流直到:

*   It takes some input from the stream.
*   Some IOException occurred.
*   It has reached the end of the stream when reading.

**语法:**

```
public int read()
```

**参数:**该方法不接受任何参数

**返回值:**该方法返回一个**整数值**，它是从流中读取的整数值。范围可以从 0 到 65535。否则，如果未读取任何字符，则返回-1。

**异常:**如果输入输出时出现错误，该方法抛出**异常**。

下面的方法说明了 read()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PushbackReader read() method

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

            // Get the character
            // to be read from the stream
            int ch;

            // Read the first 5 characters
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            for (int i = 0; i < 5; i++) {
                ch = pushbackReader.read();
                System.out.println("\nInteger value "
                                   + "of character read: "
                                   + ch);
                System.out.println("Actual "
                                   + "character read: "
                                   + (char)ch);
            }

            // Close the stream using read()
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
Integer value of character read: 71
Actual character read: G

Integer value of character read: 101
Actual character read: e

Integer value of character read: 101
Actual character read: e

Integer value of character read: 107
Actual character read: k

Integer value of character read: 115
Actual character read: s
Stream Closed.

```

**程序二:**

```
// Java program to demonstrate
// PushbackReader read() method

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

            // Get the character
            // to be read from the stream
            int ch;

            // Read the first 2 characters
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            for (int i = 0; i < 2; i++) {
                ch = pushbackReader.read();
                System.out.println("\nInteger value "
                                   + "of character read: "
                                   + ch);
                System.out.println("Actual "
                                   + "character read: "
                                   + (char)ch);
            }

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
Integer value of character read: 71
Actual character read: G

Integer value of character read: 70
Actual character read: F
Stream Closed.

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/puback reader . html # read–](https://docs.oracle.com/javase/9/docs/api/java/io/PushbackReader.html#read--)