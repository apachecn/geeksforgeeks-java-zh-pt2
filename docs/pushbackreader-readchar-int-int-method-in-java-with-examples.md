# 推读回读(char，int，int)方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/puback reader-readchar-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackreader-readchar-int-int-method-in-java-with-examples/)

Java 中 **[【推回阅读器类】](https://www.geeksforgeeks.org/java-io-pushbackreader-class-java/)** 的 **read(char[]，int，int)** 方法用于将指定长度的字符读入到指定偏移量的数组中。这个方法阻塞流直到:

*   It takes some input from the stream.
*   Some IOException occurred.
*   It has reached the end of the stream when reading.

**语法:**

```
public int read(char[] charArray, 
                     int offset, 
                     int length) 
```

**参数:**此方法接受三个强制参数:

*   **Chararray** , which is an array of characters to be written into the stream.
*   **Offset** is the offset index for writing characters in the array.
*   **Length** is the number of characters to be written in the array.

**返回值:**该方法返回一个**整数值**，即从流中读取的字符数。如果未读取任何字符，则返回-1。

**异常:**如果输入输出时出现错误，该方法抛出以下异常:

*   **Exception:** .
*   **Index out of bounds exception:** If the offset value is not in the character array

的范围内

下面的方法说明了 read(char[]，int，int)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PushbackReader read(char, int, int) method

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

            // Get the character array
            // to be read from the stream
            char[] charArray = new char[5];

            // Get the offset index
            int offset = 0;

            // Get the length
            int length = 5;

            // Read the charArray
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            pushbackReader
                .read(charArray, offset, length);

            // Print the read charArray
            System.out.println(
                Arrays.toString(charArray));

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
[G, e, e, k, s]
Stream Closed.

```

**程序二:**

```
// Java program to demonstrate
// PushbackReader read(char, int, int) method

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

            // Get the character array
            // to be read from the stream
            char[] charArray = new char[5];

            // Get the offset index
            int offset = 0;

            // Get the length
            int length = 2;

            // Read the charArray
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            pushbackReader
                .read(charArray, offset, length);

            // Print the read charArray
            System.out.println(
                Arrays.toString(charArray));

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
[G, F,,, ]
Stream Closed.

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/puback reader . html # read-char:A-int-int-](https://docs.oracle.com/javase/9/docs/api/java/io/PushbackReader.html#read-char:A-int-int-)