# Java 中的推回输入流读取()方法，示例

> 原文:[https://www . geesforgeks . org/pubackinputstream-read-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pushbackinputstream-read-method-in-java-with-examples/)

Java 中**推回输入流**类的 **read()** 方法有两种类型:

1.  The **read()** method of **PushbackInputStream** class in Java is used to read the next byte of data from the input stream. This method returns the read byte from the input stream in the form of an integer.

    **语法:**

    ```
    public int read()
              throws IOException

    ```

    **覆盖:**该方法覆盖 **FilterInputStream** 类的 read()方法。

    **参数:**此方法不接受任何参数。

    **返回值:**这个方法返回流的下一个字节。如果流结束，它将返回-1。

    **异常:**如果通过调用同一个类的 close()方法关闭了输入流，或者出现了 I/O 错误，那么这个方法抛出 **IOException** 。

    以下程序说明了输入输出包中推回输入流类的 read()方法:

    **程序 1:**

    ```
    // Java program to illustrate
    // PushbackInputStream read() method

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
                System.out.println(
                    "Char : "
                    + (char)pushbackInputStr.read());
            }
        }
    }
    ```

    **Output:**

    ```
    Char : G
    Char : E
    Char : E
    Char : K
    Char : S

    ```

    **程序 2:**

    ```
    // Java program to illustrate
    // PushbackInputStream read() method

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

            for (int i = 0; i < byteArray.length; i++) {
                System.out.println(
                    "Char : "
                    + (char)pushbackInputStr.read());
            }
        }
    }
    ```

    **Output:**

    ```
    Char : G
    Char : E
    Char : E
    Char : K
    Char : S
    Char : F
    Char : O
    Char : R
    Char : G
    Char : E
    Char : E
    Char : K
    Char : S

    ```

2.  The **read(byte[], int, int)** method of **PushbackInputStream** class in Java is used to reads up to given bytes of data from the input stream into an array of bytes. This method does not read one character at a time, it reads several characters at one time.

    **语法:**

    ```
    public int read(byte[] b,
                    int offset,
                    int length)
             throws IOException

    ```

    **覆盖:**该方法覆盖 **FilterInputStream** 类的 read()方法。

    **参数:**此方法不接受三个参数:

    *   **b**–表示读取数据的字节数组。
    *   **偏移量**–表示数组中的起始索引。
    *   **长度**–表示要读取的字节数。

    **返回值:**此方法返回读取的字节总数。如果流结束，它将返回-1。

    **异常:**

    *   **NullPointRexception**–如果字节数组为空，该方法抛出 NullPointRexception。
    *   **IndexOutOfBoundsException**–如果偏移量为负或长度为负或长度大于数组长度与偏移量之差，则该方法抛出 IndexOutOfBoundsException。
    *   **IOException**–如果通过调用同一个类的 close()方法关闭了输入流，或者出现了 I/O 错误，那么这个方法抛出 **IOException** 。

    以下程序举例说明了 IO 包中推回输入流类的 read(byte[]，int，int)方法:

    **程序 1:**

    ```
    // Java program to illustrate
    // PushbackInputStream
    // read(byte[], int, int) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
            throws IOException
        {

            // Create buffer
            byte[] b = new byte[1024];

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

            pushbackInputStr.read(b, 0, 4);

            for (int i = 0; i < 4; i++) {
                System.out.print((char)b[i]);
            }
        }
    }
    ```

    **Output:**

    ```
    GEEK

    ```

    **程序 2:**

    ```
    // Java program to illustrate
    // PushbackInputStream
    // read(byte[], int, int) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
            throws IOException
        {

            // Create buffer
            byte[] b = new byte[1024];

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

            pushbackInputStr.read(b, 8, 5);

            for (int i = 8; i < 13; i++) {
                System.out.print((char)b[i]);
            }
        }
    }
    ```

    **Output:**

    ```
    GEEKS

    ```

**参考资料:**
1。[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbakinputstream . html # read()](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#read())t5]2。[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbaenpputstream . html # read(位元组%5B%5D，int，int)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#read(byte%5B%5D, int, int))