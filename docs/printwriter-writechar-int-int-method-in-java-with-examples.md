# PrintWriter 用 Java 写(char[]，int，int)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-write char-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-writechar-int-int-method-in-java-with-examples/)

Java 中**[【PrintWriter】](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)**类的 **write(char[]，int，int)** 方法用于在流中写入指定字符数组的指定部分。这个字符数组作为一个参数。要写入的字符的起始索引和长度也作为参数。

**语法:**

> public void write(char[]char array、int startingIndex、int lengthofchararray)

**参数:**该方法接受三个强制参数:

*   **字符数组**是要写入流中的字符数组。
*   **起始索引**是字符部分的起始索引。
*   **长度字符串**是要写入流中的字符长度。

**返回值:**此方法不返回值。

下面的方法说明了 write(char[]，int，int)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintWriter write(char[], int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the character array
            // to be written in the stream
            char[] charArray = { 'G', 'e', 'e', 'k', 's',
                                 'F', 'o', 'r',
                                 'G', 'e', 'e', 'k', 's' };

            // Get the starting index
            int startingIndex = 0;

            // Get the length of char
            int lengthOfCharArray = 5;

            // Write the portion of the charArray
            // to this writer using write() method
            // This will put the charArray in the stream
            // till it is printed on the console
            writer.write(charArray,
                         startingIndex,
                         lengthOfCharArray);

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
// PrintWriter write(char[], int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the character array
            // to be written in the stream
            char[] charArray = { 'G', 'F', 'G' };

            // Get the starting index
            int startingIndex = 2;

            // Get the length of char
            int lengthOfCharArray = 1;

            // Write the portion of the charArray
            // to this writer using write() method
            // This will put the charArray in the stream
            // till it is printed on the console
            writer.write(charArray,
                         startingIndex,
                         lengthOfCharArray);

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