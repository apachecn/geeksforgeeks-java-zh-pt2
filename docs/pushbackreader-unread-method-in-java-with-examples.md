# Java 中的推读未读()方法，示例

> 原文:[https://www . geesforgeks . org/puback reader-未读-java 中的方法-带示例/](https://www.geeksforgeeks.org/pushbackreader-unread-method-in-java-with-examples/)

Java 中**推回阅读器**类的**未读()**方法有三种类型:

1.  The **unread(int c)** method of **PushbackReader** class in Java is used to push back a character by copying it to the front of the pushback buffer. After revoking this method, when the next character is read it has the value equal to the parameter passed.

    **语法:**

    ```java
    public void unread(int c)
                throws IOException

    ```

    **参数:**该方法接受一个参数 c，该参数 c 代表待推回字符的整数值。

    **返回值:**此方法不返回值。

    **异常:**如果推回缓冲区已满或出现输入/输出错误，此方法将引发**异常**。

    下面的程序说明了 IO 包中推包阅读器类的未读(int)方法:

    **程序 1:**

    ```java
    // Java program to illustrate
    // PushbackReader unread(int) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
            throws IOException
        {

            // Create string
            String str = "GEEKS";

            // Create stringReader
            StringReader strReader
                = new StringReader(str);

            // Create object of
            // PushbackReader
            PushbackReader pushbackReader
                = new PushbackReader(strReader, 100);

            for (int i = 0; i < str.length(); i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }

            // Call unread() method
            pushbackReader.unread(65);

            System.out.print(
                "\n"
                + (char)pushbackReader.read());
        }
    }
    ```

    **Output:**

    ```java
    GEEKS
    A

    ```

    **程序 2:**

    ```java
    // Java program to illustrate
    // PushbackReader unread(int) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
            throws IOException
        {

            // Create string
            String str = "GEEKSFORGEEKS";

            // Create stringReader
            StringReader strReader
                = new StringReader(str);

            // Create object of
            // PushbackReader
            PushbackReader pushbackReader
                = new PushbackReader(strReader, 100);

            for (int i = 0; i < str.length(); i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }

            // Call unread() method
            pushbackReader.unread('Z');

            System.out.print(
                "\n"
                + (char)pushbackReader.read());
        }
    }
    ```

    **Output:**

    ```java
    GEEKSFORGEEKS
    Z

    ```

2.  The **unread(char[] cbuf)** method of **PushbackReader** class in Java is used to push back an array of characters by copying it to the front of the pushback buffer. After revoking this method, when the next character is read it has the value equal to the first element of the character array.

    **语法:**

    ```java
    public void unread(char[] cbuf)
                throws IOException

    ```

    **参数:**该方法接受一个参数 **cbuf** ，表示待推回的字符数组。

    **返回值:**此方法不返回值。

    **异常:**如果推回缓冲区已满或出现输入/输出错误，此方法将引发**异常**。

    以下程序说明了 IO 包中推包阅读器类的未读(char[])方法:

    **程序 1:**

    ```java
    // Java program to illustrate
    // PushbackReader unread(char[]) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
            throws IOException
        {

            // Create string
            String str = "GEEKS";

            // Create stringReader
            StringReader strReader
                = new StringReader(str);

            // Create object of
            // PushbackReader
            PushbackReader pushbackReader
                = new PushbackReader(strReader, 100);

            for (int i = 0; i < str.length(); i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }

            // Create character array
            char[] cbuf = new char[] { 'A', 'B', 'C' };

            // Call unread() method
            pushbackReader.unread(cbuf);

            System.out.println();

            for (int i = 0; i < cbuf.length; i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }
        }
    }
    ```

    **Output:**

    ```java
    GEEKS
    ABC

    ```

    **程序 2:**

    ```java
    // Java program to illustrate
    // PushbackReader unread(char[]) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
            throws IOException
        {

            // Create string
            String str = "GEEKSFORGEEKS";

            // Create stringReader
            StringReader strReader
                = new StringReader(str);

            // Create object of
            // PushbackReader
            PushbackReader pushbackReader
                = new PushbackReader(strReader, 100);

            for (int i = 0; i < str.length(); i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }

            // Create character array
            char[] cbuf = new char[] { 'X', 'Y', 'Z' };

            // Call unread() method
            pushbackReader.unread(cbuf);

            System.out.println();

            for (int i = 0; i < cbuf.length; i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }
        }
    }
    ```

    **Output:**

    ```java
    GEEKSFORGEEKS
    XYZ

    ```

3.  The **unread(char[] cbuf, int offset, int length)** method of **PushbackReader** class in Java is used to push back a part of an array of characters by copying it to the front of the pushback buffer. After revoking this method, when the next character is read it has the value equal to the first element of the portion of the given character array.

    **语法:**

    ```java
    public void unread(char[] cbuf,
                       int offset,
                       int length)
                throws IOException

    ```

    **参数:**该方法接受三个参数:

    *   **cbuf**–它代表字符数组，其一部分将被推送。
    *   **偏移量**–表示字符数组部分的起始索引。
    *   **长度**–表示需要推送的字符数。

    **返回值:**此方法不返回值。

    **异常:**如果推回缓冲区中没有足够的空间或者出现输入/输出错误，此方法将引发**异常**。

    下面的程序说明了 IO 包中推包阅读器类的未读(char[]，int，int)方法:

    **程序 1:**

    ```java
    // Java program to illustrate
    // PushbackReader
    // unread(char[], int, int) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
            throws IOException
        {

            // Create string
            String str = "GEEKS";

            // Create stringReader
            StringReader strReader
                = new StringReader(str);

            // Create object of
            // PushbackReader
            PushbackReader pushbackReader
                = new PushbackReader(strReader, 100);

            for (int i = 0; i < str.length(); i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }

            // Create character array
            char[] cbuf
                = new char[] { 'A', 'B', 'C',
                               'D', 'E' };

            // Call unread() method
            pushbackReader.unread(cbuf, 2, 3);

            System.out.println();

            for (int i = 0; i < 3; i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }
        }
    }
    ```

    **Output:**

    ```java
    GEEKS
    CDE

    ```

    **程序 2:**

    ```java
    // Java program to illustrate
    // PushbackReader
    // unread(char[], int, int) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
            throws IOException
        {

            // Create string
            String str = "GEEKSFORGEEKS";

            // Create stringReader
            StringReader strReader
                = new StringReader(str);

            // Create object of
            // PushbackReader
            PushbackReader pushbackReader
                = new PushbackReader(strReader, 100);

            for (int i = 0; i < str.length(); i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }

            // Create character array
            char[] cbuf
                = new char[] { 'W', 'X',
                               'Y', 'Z' };

            // Call unread() method
            pushbackReader.unread(cbuf, 1, 3);

            System.out.println();

            for (int i = 0; i < 3; i++) {
                System.out.print(
                    (char)pushbackReader.read());
            }
        }
    }
    ```

    **Output:**

    ```java
    GEEKSFORGEEKS
    XYZ

    ```

**参考资料:**
1。[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbackreader . html # unread(int)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackReader.html#unread(int))T2。[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbackreader . html # unread(char % 5b % 5d)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackReader.html#unread(char%5B%5D))T3。[https://docs . Oracle . com/javae/10/docs/API/Java/io/pushbckreader . html # unread(char % 5b % 5d，int，int)](https://docs.oracle.com/javase/10/docs/api/java/io/PushbackReader.html#unread(char%5B%5D, int, int))