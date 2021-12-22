# Java 中的 PrintStream close()方法，示例

> 原文:[https://www . geesforgeks . org/print stream-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-close-method-in-java-with-examples/)

Java 中 **[PrintStream](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **close()** 方法用于关闭该流。关闭流会释放流中的任何值或与之关联的任何资源。PrintStream 实例一旦关闭就不起作用了。此外，打印流实例一旦关闭，就不能再次关闭。

**语法:**

```java
public void close()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。它只是关闭了流。

下面的方法说明了 close()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintStream close() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // The string to be written in the Stream
        String str = "GeeksForGeeks";

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Write the above string to this stream
            // This will put the string in the stream
            // till it is printed on the console
            stream.print(str);

            // Now close the stream
            // using close() method
            stream.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
GeeksForGeeks

```

**程序 2:**

```java
// Java program to demonstrate
// PrintStream close() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Write the char to this stream
            // This will put the char in the stream
            // till it is printed on the console
            stream.write(65);

            // Now close the stream
            // using close() method
            stream.close();
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