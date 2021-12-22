# Java 中的 PushbackInputStream unread()方法，示例

> 原文:[https://www . geesforgeks . org/pubackinputstream-未读-java 中的方法-带示例/](https://www.geeksforgeeks.org/pushbackinputstream-unread-method-in-java-with-examples/)

Java 中**推回输入流**类的**未读()**方法有三种类型:

1.  The **unread(int b)** method of **PushbackInputStream** class in Java is used to push back a byte by copying it to the front of the pushback buffer. After revoking this method, when the next byte is read it has the value equal to the parameter passed.

    **语法:**

    ```
    public void unread(int b)
                throws IOException

    ```

    **参数:**该方法接受一个参数 b，代表要推回的整数值。

    **返回值:**此方法不返回值。

    **异常:**如果通过调用同一个类的 close()方法关闭了输入流，或者推回缓冲区中没有足够的空间容纳该字节，则该方法抛出 **IOException** 。

    下面的程序说明了 IO 包中推回输入流类的未读(int)方法:

    **程序 1:**

    ```
    // Java program to illustrate
    // PushbackInputStream unread(int) method

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
                System.out.print(
                    (char)pushbackInputStr.read());
            }

            // Call unread() method
            pushbackInputStr.unread(65);

            System.out.print(
                "\n"
                + (char)pushbackInputStr.read());
        }
    }
    ```

    **Output:**

    ```
    GEEKS
    A

    ```

    **程序 2:**

    ```
    // Java program to illustrate
    // PushbackInputStream unread() method

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
                System.out.print(
                    (char)pushbackInputStr.read());
            }

            // Call unread() method
            pushbackInputStr.unread(90);

            System.out.print(
                "\n"
                + (char)pushbackInputStr.read());
        }
    }
    ```

    **Output:**

    ```
    GEEKSFORGEEKS
    Z

    ```

2.  The **unread(byte[] b)** method of **PushbackInputStream** class in Java is used to push back an array of byte by copying it to the front of the pushback buffer. After revoking this method, when the next byte is read it has the value equal to the first element of the byte array.

    **语法:**

    ```
    public void unread(byte[] b)
                throws IOException

    ```

    **参数:**这个方法接受一个参数 b，代表要推回的字节数组。

    **返回值:**此方法不返回值。

    **异常:**如果通过调用同一个类的 close()方法关闭输入流，或者如果推回缓冲区中没有足够的空间用于数组字节，则该方法抛出 **IOException** 。

    以下程序说明了 IO 包中推回输入流类的未读(字节[])方法:

    **程序 1:**

    ```
    // Java program to illustrate
    // PushbackInputStream unread(byte[]) method

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
                = new PushbackInputStream(inputStr, 100);

            for (int i = 0; i < byteArray.length; i++) {
                System.out.print(
                    (char)pushbackInputStr.read());
            }

            // Create byte array
            byte[] b = new byte[] { 'A', 'B', 'C' };

            // Call unread() method
            pushbackInputStr.unread(b);

            System.out.println();

            for (int i = 0; i < b.length; i++) {
                System.out.print(
                    (char)pushbackInputStr.read());
            }
        }
    }
    ```

    **Output:**

    ```
    GEEKS
    ABC

    ```

    **程序 2:**

    ```
    // Java program to illustrate
    // PushbackInputStream unread(byte[]) method

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
                = new PushbackInputStream(inputStr, 100);

            for (int i = 0; i < byteArray.length; i++) {
                System.out.print(
                    (char)pushbackInputStr.read());
            }

            // Create byte array
            byte[] b = new byte[] { 'X', 'Y', 'Z' };

            // Call unread() method
            pushbackInputStr.unread(b);

            System.out.println();

            for (int i = 0; i < b.length; i++) {
                System.out.print(
                    (char)pushbackInputStr.read());
            }
        }
    }
    ```

    **Output:**

    ```
    GEEKSFORGEEKS
    XYZ

    ```

3.  The **unread(byte[] b, int offset, int length)** method of **PushbackInputStream** class in Java is used to push back a part of an array of byte by copying it to the front of the pushback buffer. After revoking this method, when the next byte is read it has the value equal to the first element of the portion of the given byte array.

    **语法:**

    ```
    public void unread(byte[] b,
                       int offset,
                       int length)
                throws IOException

    ```

    **参数:**该方法接受三个参数:

    *   **b**–它代表字节数组，其一部分将被推送。
    *   **偏移量**–表示字节数组部分的起始索引。
    *   **长度**–表示需要推送的字节数。

    **返回值:**此方法不返回值。

    **异常:**如果通过调用同一个类的 close()方法关闭输入流，或者如果推回缓冲区中没有足够的空间用于数组字节，则该方法抛出 **IOException** 。

    下面的程序说明了 IO 包中推回输入流类的未读(byte[]，int，int)方法:

    **程序 1:**

    ```
    // Java program to illustrate
    // PushbackInputStream
    // unread(byte[], int, int) method

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
                = new PushbackInputStream(inputStr, 100);

            for (int i = 0; i < byteArray.length; i++) {
                System.out.print(
                    (char)pushbackInputStr.read());
            }

            // Create byte array
            byte[] b
                = new byte[] { 'A', 'B', 'C',
                               'D', 'E' };

            // Call unread() method
            pushbackInputStr.unread(b, 2, 3);

            System.out.println();

            for (int i = 0; i < 3; i++) {
                System.out.print(
                    (char)pushbackInputStr.read());
            }
        }
    }
    ```

    **Output:**

    ```
    GEEKS
    CDE

    ```

    **程序 2:**

    ```
    // Java program to illustrate
    // PushbackInputStream
    // unread(byte[], int, int) method

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
                = new PushbackInputStream(inputStr, 100);

            for (int i = 0; i < byteArray.length; i++) {
                System.out.print(
                    (char)pushbackInputStr.read());
            }

            // Create byte array
            byte[] b = new byte[] { 'W', 'X', 'Y', 'Z' };

            // Call unread() method
            pushbackInputStr.unread(b, 1, 3);

            System.out.println();

            for (int i = 0; i < 3; i++) {
                System.out.print(
                    (char)pushbackInputStr.read());
            }
        }
    }
    ```

    **Output:**

    ```
    GEEKSFORGEEKS
    XYZ

    ```

**参考资料:**
1。[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbakinputstream . html # unread(int)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#unread(int))t5]2。[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbaknpertstream . html # unread(字节% 5b % 5d)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#unread(byte%5B%5D))t8]3。[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbaenpputstream . html # unread(字节%5B%5D，int，int)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackInputStream.html#unread(byte%5B%5D, int, int))