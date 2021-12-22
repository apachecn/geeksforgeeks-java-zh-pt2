# Java 中的推回输入流跳过()方法，示例

> 原文:[https://www . geesforgeks . org/pubackinputstream-skip-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackinputstream-skip-method-in-java-with-examples/)

Java 中**推回输入流**类的**跳过(长 n)** 方法用于跳过并丢弃该输入流中的 n 字节数据。这个方法首先跳过推回缓冲区中的字节，然后调用主输入流的 skip 方法。它返回实际跳过的字节数。

**语法:**

```
public long skip(long n)
           throws IOException

```

**覆盖:**该方法覆盖 **FilterInputStream** 类的 skip()方法。

**参数:**这个方法接受一个参数 n，代表要跳过的字节数。

**返回值:**此方法返回实际跳过的字节数。

**异常:**如果已经通过调用 close()方法关闭了流，或者发生了 I/O 错误，则该方法抛出 **IOException** 。

以下程序说明了 IO 包中推回输入流类的跳过(长)方法:

**程序 1:**

```
// Java program to illustrate
// PushbackInputStream skip(long) method

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

        // Revoke skip()
        pushbackInputStr.skip(2);

        for (int i = 0; i < byteArray.length - 2; i++) {
            // Read the character
            System.out.print(
                (char)pushbackInputStr.read());
        }
    }
}
```

**Output:**

```
EKS

```

**程序 2:**

```
// Java program to illustrate
// PushbackInputStream skip(long) method

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

        // Revoke skip()
        pushbackInputStr.skip(8);

        for (int i = 0; i < byteArray.length - 8; i++) {
            // Read the character
            System.out.print(
                (char)pushbackInputStr.read());
        }
    }
}
```

**Output:**

```
GEEKS

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/pubackinputstream . html # skip(长)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#skip(long))