# StringReader 读取 Java 中的(char[]，int，int)方法，示例

> 原文:[https://www . geeksforgeeks . org/string reader-readchar-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringreader-readchar-int-int-method-in-java-with-examples/)

Java 中**[【StringReader】](https://www.geeksforgeeks.org/java-io-stringreader-class-java/)**类的 **read(char[]，int，int)** 方法用于将指定长度的字符读入到指定偏移量的数组中。这个方法阻塞流直到:

*   It takes some input from the stream.
*   Some IOException occurred.
*   It has reached the end of the stream when reading.

**语法:**

> **公共 int read(char[] charArray，int offset，int length)**

**参数:**该方法接受三个强制参数:

*   **字符数组**是要写入流中的字符数组。
*   **偏移量**是数组中字符写入的偏移量索引。
*   **长度**是数组中要写入的字符数。

**返回值:**该方法返回一个**整数值**，即从流中读取的字符数。如果未读取任何字符，则返回-1。

**异常:**如果输入输出时出现错误，该方法抛出以下异常:

*   **Exception:** .
*   **Index out of bounds exception:** If the offset value is not in the character array

的范围内

下面的方法说明了 read(char[]，int，int)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// StringReader read(char[], int, int) method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            String str = "GeeksForGeeks";

            // Create a StringReader instance
            StringReader reader
                = new StringReader(str);

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
            reader.read(charArray, offset, length);

            // Print the read charArray
            System.out.println(
                Arrays.toString(charArray));

            reader.close();
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

```

**程序二:**

```
// Java program to demonstrate
// StringReader read(char[], int, int) method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            String str = "GeeksForGeeks";

            // Create a StringReader instance
            StringReader reader
                = new StringReader(str);

            // Get the character array
            // to be read from the stream
            char[] charArray
                = new char[13];

            // Get the offset index
            int offset = 0;

            // Get the length
            int length = 13;

            // Read the charArray
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            reader.read(charArray, offset, length);

            // Print the read charArray
            System.out.println(
                Arrays.toString(charArray));

            reader.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
[G, e, e, k, s, F, o, r, G, e, e, k, s]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/stringreader . html # read-char:A-int-int-](https://docs.oracle.com/javase/9/docs/api/java/io/StringReader.html#read-char:A-int-int-)