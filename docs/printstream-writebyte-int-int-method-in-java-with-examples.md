# Java 中的 PrintStream write(byte[]，int，int)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-write byte-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-writebyte-int-int-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **write(byte[]，int，int)** 方法用于在流上写入指定字节字符数组的指定部分。这个字节字符数组被作为一个参数。要写入的字节字符的起始索引和长度也作为参数。

**语法:**

> public void write(字节[]字节数组、int startingIndex、int lengthofchararray)

**参数:**该方法接受三个强制参数:

*   **字节数组**是要写入流中的字节字符数组。
*   **startingIndex** 是开始索引，从该索引中获取字节字符的一部分。
*   **长度字符串**是要写入流中的字节字符的长度。

**返回值:**此方法不返回值。

下面的方法说明了 write(byte[]，int，int)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintStream write(byte[], int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Get the byteacter array
            // to be written in the stream
            byte[] byteArray = { 65, 66, 67 };

            // Get the starting index
            int startingIndex = 0;

            // Get the length of byte
            int lengthOfCharArray = 1;

            // Write the portion of the byteArray
            // to this stream using write() method
            // This will put the byteArray in the stream
            // till it is printed on the console
            stream.write(byteArray,
                         startingIndex,
                         lengthOfCharArray);

            stream.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
A

```

**程序 2:**

```
// Java program to demonstrate
// PrintStream write(byte[], int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Get the byteacter array
            // to be written in the stream
            byte[] byteArray = { 97, 98, 99 };

            // Get the starting index
            int startingIndex = 2;

            // Get the length of byte
            int lengthOfCharArray = 1;

            // Write the portion of the byteArray
            // to this stream using write() method
            // This will put the byteArray in the stream
            // till it is printed on the console
            stream.write(byteArray,
                         startingIndex,
                         lengthOfCharArray);

            stream.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
c

```