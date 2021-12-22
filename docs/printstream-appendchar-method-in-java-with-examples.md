# Java 中的打印流追加(char)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-append char-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-appendchar-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的**追加(char)** 方法用于在流上追加指定的 char 值。这个字符值被作为一个参数。

**语法:**

```
public void append(char charValue)
```

**参数:**该方法接受一个强制参数**字符值**，它是要附加到流上的字符值。

**返回值:**此方法不返回值。

下面的方法说明了 append(char)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintStream append(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Append the char value 'A'
            // to this stream using append() method
            // This will put the charValue in the
            // stream till it is appended on the console
            stream.append('A');

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
// PrintStream append(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Append the char value 'G'
            // to this stream using append() method
            // This will put the charValue in the
            // stream till it is appended on the console
            stream.append('G');

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
G

```