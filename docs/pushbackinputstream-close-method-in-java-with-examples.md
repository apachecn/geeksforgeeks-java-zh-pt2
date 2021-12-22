# Java 中的推回输入流关闭()方法，示例

> 原文:[https://www . geeksforgeeks . org/pubackinputstream-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackinputstream-close-method-in-java-with-examples/)

Java 中**推回输入流**类的 **close()** 方法用于关闭输入流，并释放与该流相关联的系统资源。在调用这个方法之后，如果这个类将抛出 IOException，则进一步调用其他方法。

**语法:**

```
public void close()
           throws IOException

```

**指定者:**该方法由**可自动关闭**界面的关闭()方法和**可关闭**界面的关闭()方法指定。

**覆盖:**该方法覆盖 **FilterInputStream** 类的 close()方法。

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**如果出现输入输出错误，该方法抛出**异常**。

以下程序说明了输入输出包中推回输入流类的 close()方法:

**程序 1:**

```
// Java program to illustrate
// PushbackInputStream close() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {
        try {

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

            // Revoke close()
            pushbackInputStr.close();
        }
        catch (Exception e) {
            System.out.println("Stream is closed");
        }
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
// PushbackInputStream close() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {
        try {

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

            // Revoke close()
            pushbackInputStr.close();

            for (int i = 0; i < byteArray.length; i++) {
                // Read the character
                System.out.print(
                    (char)pushbackInputStr.read());
            }
        }
        catch (Exception e) {
            System.out.println("Stream is closed");
        }
    }
}
```

**Output:**

```
Stream is closed

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/pubackinputstream . html # close()](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#close())