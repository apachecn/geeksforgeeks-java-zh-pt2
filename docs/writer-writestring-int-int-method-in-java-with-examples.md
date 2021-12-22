# 编写器用 Java 编写(String，int，int)方法，示例

> 原文:[https://www . geesforgeks . org/writer-write string-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/writer-writestring-int-int-method-in-java-with-examples/)

Java 中 **[Writer](https://www.geeksforgeeks.org/java-io-Writer-class-java-set-1/)** 类的 **write(String，int，int)** 方法用于在流中写入指定字符串的指定部分。该字符串被视为参数。要写入的字符串的起始索引和长度也作为参数。

**语法:**

> 公共空写(字符串，int startingIndex，int lengthOfstring)

**参数:**该方法接受三个强制参数:

*   **字符串**是要写入流中的字符串。
*   **起始索引**是字符部分的起始索引。
*   **字符串长度**是要写入流中的字符串长度。

**返回值:**此方法不返回值。

下面的方法说明了 write(String，int，int)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// Writer write(String, int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Get the String
            // to be written in the stream
            String string = "GeeksForGeeks";

            // Get the starting index
            int startingIndex = 0;

            // Get the length of char
            int lengthOfstring = 5;

            // Write the portion of the string
            // to this writer using write() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.write(string,
                         startingIndex,
                         lengthOfstring);

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Geeks

```

**程序 2:**

```
// Java program to demonstrate
// Writer write(String, int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Get the String
            // to be written in the stream
            String string = "GFG";

            // Get the starting index
            int startingIndex = 2;

            // Get the length of char
            int lengthOfstring = 1;

            // Write the portion of the string
            // to this writer using write() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.write(string,
                         startingIndex,
                         lengthOfstring);

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
G

```