# Java 中的 PrintStream println(char)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-printlnchar-method-in-Java-with-examples-2/](https://www.geeksforgeeks.org/printstream-printlnchar-method-in-java-with-examples-2/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **println(char)** 方法是将指定的 char 值打印在流上，然后换行。这个字符值被作为一个参数。

**语法:**

```
public void println(char charValue)
```

**参数:**该方法接受一个强制参数 **charValue** ，即要写入流的 char 值。

**返回值:**此方法不返回值。

下面的方法说明了 println(char)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintStream println(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the char value 'A'
            // to this stream using println() method
            // This will put the charValue in the
            // stream till it is printed on the console
            stream.println('A');

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
// PrintStream println(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the char value 'G'
            // to this stream using println() method
            // This will put the charValue in the
            // stream till it is printed on the console
            stream.println('G');

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