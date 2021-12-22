# Java 中 PrintWriter close()方法，带示例

> 原文:[https://www . geesforgeks . org/print writer-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-close-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的 **close()** 方法用于关闭流。关闭流会释放流中的任何值或与之关联的任何资源。PrintWriter 实例一旦关闭就不起作用了。此外，PrintWriter 实例一旦关闭，就不能再次关闭。

**语法:**

```
public void close()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。它只是关闭了流。

下面的方法说明了 close()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintWriter close() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // The string to be written in the Writer
        String str = "GeeksForGeeks";

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the above string to this writer
            // This will put the string in the stream
            // till it is printed on the console
            writer.write(str);

            // Now close the stream
            // using close() method
            writer.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
GeeksForGeeks

```

**程序 2:**

```
// Java program to demonstrate
// PrintWriter close() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the char to this writer
            // This will put the char in the stream
            // till it is printed on the console
            writer.write(65);

            // Now close the stream
            // using close() method
            writer.close();
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