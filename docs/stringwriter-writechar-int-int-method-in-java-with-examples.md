# StringWriter 用 Java 写(char[]，int，int)方法，示例

> 原文:[https://www . geeksforgeeks . org/stringwriter-write char-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringwriter-writechar-int-int-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的 **write(char[]，int，int)** 方法用于在 Writer 上写入指定字符数组的指定部分。这个字符数组作为一个参数。要写入的字符的起始索引和长度也作为参数。

**语法:**

> public void write(char[]char array、int startingIndex、int lengthofchararray)

**参数:**该方法接受三个强制参数:

*   **字符数组**是写入程序中要写入的字符数组。
*   **起始索引**是字符部分的起始索引。
*   **chararray length**写在书写器上的字符长度。

**返回值:**此方法不返回值。

下面的程序说明了 write(char[]，int，int)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// StringWriter write(char[], int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Get the character array
            // to be written in the writer
            char[] charArray = { 65, 66, 67 };

            // Get the starting index
            int startingIndex = 0;

            // Get the length of char
            int lengthOfCharArray = 1;

            // Write the portion of the charArray
            // to this writer using write() method
            // This will put the charArray in the writer
            // till it is printed on the console
            writer.write(charArray,
                         startingIndex,
                         lengthOfCharArray);

            System.out.println(writer.toString());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
A

```

**程序 2:**

```java
// Java program to demonstrate
// StringWriter write(char[], int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Get the character array
            // to be written in the writer
            char[] charArray = { 97, 98, 99 };

            // Get the starting index
            int startingIndex = 2;

            // Get the length of char
            int lengthOfCharArray = 1;

            // Write the portion of the charArray
            // to this writer using write() method
            // This will put the charArray in the writer
            // till it is printed on the console
            writer.write(charArray,
                         startingIndex,
                         lengthOfCharArray);

            System.out.println(writer.toString());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
c

```