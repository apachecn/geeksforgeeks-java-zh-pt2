# Java 中的推回输入流重置()方法，示例

> 原文:[https://www . geesforgeks . org/pubackinputstream-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackinputstream-reset-method-in-java-with-examples/)

Java 中**推回输入流**类的 **reset()** 方法用于将蒸汽重置到调用 mark()方法的位置。这个方法对推回输入流没有任何作用。

**语法:**

```java
public void reset()
           throws IOException

```

**覆盖:**该方法覆盖 **FilterInputStream** 类的 reset()方法。

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**每当调用此方法时，此方法都会抛出 **IOException** 。

以下程序说明了输入输出包中推回输入流类的重置()方法:

**程序 1:**

```java
// Java program to illustrate
// PushbackInputStream reset() method

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

        // Revoke reset() but it does nothing
        pushbackInputStr.reset();
    }
}
```

**Output:**

> 线程“main”中出现异常 java.io.IOException:不支持标记/重置
> GEEKS

**程序 2:**

```java
// Java program to illustrate
// PushbackInputStream reset() method

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

        // Revoke reset()
        pushbackInputStr.reset();

        for (int i = 0; i < byteArray.length; i++) {
            // Read the character
            System.out.print(
                (char)pushbackInputStr.read());
        }
    }
}
```

**Output:**

> 线程“main”Java . io . ioexception 中的异常:不支持标记/重置

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbaeputstream . html # reset()](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#reset())