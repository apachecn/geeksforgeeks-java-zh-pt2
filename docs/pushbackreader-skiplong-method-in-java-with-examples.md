# Java 中的推读跳过(长)方法，示例

> 原文:[https://www . geesforgeks . org/puback reader-skip long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackreader-skiplong-method-in-java-with-examples/)

Java 中 **[推读类](https://www.geeksforgeeks.org/java-io-pushbackreader-class-java/)** 的**跳过(长)**方法用于跳过流中指定数量的字符。这个字符数被指定为参数。如果它通过跳过到达流的末尾，它将阻塞流，直到它得到一些字符，或者抛出 IOException。

**语法:**

```java
public long skip(long numberOfChar)
```

**参数:**这个方法接受一个参数 **numberOfChar** ，这是这个方法要跳过的字符数。

**返回值:**该方法返回一个**长值**，即该方法实际跳过的字符数。

**异常:**如果在输入输出

*   There are some errors in **. This method throws:

    *   **Exception:** If the number of Char passed is negative,** 

下面的方法说明了跳(长)法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PushbackReader skip(long) method

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
                System.out.print((char)ch);
            }

            System.out.println();

            // skip 3 characters using skip(long)
            pushbackReader.skip(3);

            System.out.println("Next 3 characters skipped.");

            // Read the 2 characters
            // to this reader using read() method
            for (int i = 0; i < 2; i++) {
                ch = pushbackReader.read();
                System.out.print((char)ch);
            }

            System.out.println();

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
Geeks
Next 3 characters skipped.
Ge
Stream Closed.

```

**程序二:**

```java
// Java program to demonstrate
// PushbackReader skip(long) method

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

            // Read the first character
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            ch = pushbackReader.read();
            System.out.print((char)ch);

            System.out.println();

            // skip 1 characters using skip(long)
            pushbackReader.skip(1);

            System.out.println("Next 1 characters skipped.");

            // Read the next 1 character
            // to this reader using read() method
            for (int i = 0; i < 1; i++) {
                ch = pushbackReader.read();
                System.out.print((char)ch);
            }

            System.out.println();

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
G
Next 1 characters skipped.
G
Stream Closed.

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/puback reader . html # skip-long-](https://docs.oracle.com/javase/9/docs/api/java/io/PushbackReader.html#skip-long-)