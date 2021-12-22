# Java 中的推回输入流标记()方法，示例

> 原文:[https://www . geesforgeks . org/pubackinputstream-mark-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackinputstream-mark-method-in-java-with-examples/)

Java 中**推回输入流**类的**标记()**方法用于标记输入流中的当前位置。这个方法对推回输入流没有任何作用。

**语法:**

```
public void mark(int readlimit)

```

**覆盖:**该方法覆盖 **FilterInputStream** 类的 mark()方法。

**参数:**该方法接受单个参数 **readlimit** ，表示在标记位置无效之前可以读取的最大字节数限制。

**返回值:**此方法不返回值。

**异常:**此方法不抛出任何异常。

以下程序说明了输入输出包中推回输入流类的 mark()方法:

**程序 1:**

```
// Java program to illustrate
// PushbackInputStream mark() method

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

        for (int i = 0; i < byteArray.length; i++) {
            // Read the character
            System.out.print(
                (char)pushbackInputStr.read());
        }

        // Revoke mark() but it does nothing
        pushbackInputStr.mark(5);
    }
}
```

**Output:**

```
GEEKS

```

**程序 2:**

```
// Java program to illustrate
// PushbackInputStream mark() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create an array
        byte[] byteArray
            = new byte[] { 'H', 'E', 'L',
                           'L', 'O' };

        // Create inputStream
        InputStream inputStr
            = new ByteArrayInputStream(byteArray);

        // Create object of
        // PushbackInputStream
        PushbackInputStream pushbackInputStr
            = new PushbackInputStream(inputStr);

        // Revoke mark()
        pushbackInputStr.mark(1);

        for (int i = 0; i < byteArray.length; i++) {
            // Read the character
            System.out.print(
                (char)pushbackInputStr.read());
        }
    }
}
```

**Output:**

```
HELLO

```

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbaenpingstream . html # mark(int)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#mark(int))