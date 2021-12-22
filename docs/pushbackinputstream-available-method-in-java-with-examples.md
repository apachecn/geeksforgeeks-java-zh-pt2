# Java 中可用的推回输入流()方法，示例

> 原文:[https://www . geeksforgeeks . org/pubackinputstream-Java 中可用的方法-示例/](https://www.geeksforgeeks.org/pushbackinputstream-available-method-in-java-with-examples/)

Java 中**PubackInputStream**类的**可用()**方法用于查找可以从输入流中读取而不阻塞的字节数。它返回这个字节数的估计值。它可能会被同一输入流的下一次方法调用阻塞。

**语法:**

```
public int available()
              throws IOException

```

**覆盖:**该方法覆盖 **FilterInputStream** 类的可用()方法。

**参数:**此方法不接受任何参数。

**返回值:**此方法返回可以从输入流中读取而不阻塞的字节数。

**异常:**如果通过调用同一个类的 close()方法关闭了输入流，或者出现了 I/O 错误，那么这个方法抛出 **IOException** 。

以下程序说明了输入输出包中推回输入流类的可用()方法:

**程序 1:**

```
// Java program to illustrate
// PushbackInputStream available() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create an array
        byte[] byteArray
            = new byte[] { 'G', 'E', 'E',
                           'K', 'S' };

        // Create inputStream
        InputStream inputStr
            = new ByteArrayInputStream(byteArray);

        // Create object of
        // PushbackInputStream
        PushbackInputStream pushbackInputStr
            = new PushbackInputStream(inputStr);

        // Find number of bytes
        int total_bytes
            = pushbackInputStr.available();

        System.out.println(
            "Total Bytes : " + total_bytes);
    }
}
```

**Output:**

```
Total Bytes : 5

```

**程序 2:**

```
// Java program to illustrate
// PushbackInputStream available() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create an array
        byte[] byteArray
            = new byte[] { 'G', 'E', 'E', 'K', 'S',
                           'F', 'O', 'R', 'G', 'E',
                           'E', 'K', 'S' };

        // Create inputStream
        InputStream inputStr
            = new ByteArrayInputStream(byteArray);

        // Create object of
        // PushbackInputStream
        PushbackInputStream pushbackInputStr
            = new PushbackInputStream(inputStr);

        // Print total bytes
        System.out.println(
            "Total Bytes : "
            + pushbackInputStr.available());
    }
}
```

**Output:**

```
Total Bytes : 13

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/pubackinputstream . html # available()](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#available())