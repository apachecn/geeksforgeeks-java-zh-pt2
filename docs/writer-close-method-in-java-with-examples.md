# 用示例在 Java 中编写 close()方法

> 原文:[https://www . geesforgeks . org/writer-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/writer-close-method-in-java-with-examples/)

Java 中**close()**[Writer](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)**类的**方法用来关闭 Writer。关闭编写器会释放其中的任何值或与之关联的任何资源。Writer 实例一旦关闭将无法工作。此外，Writer 实例一旦关闭，就不能再次关闭。

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
// Writer close() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // The string to be written in the Stream
        String str = "GeeksForGeeks";

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Write the above string to this writer
            // This will put the string in the writer
            // till it is printed on the console
            writer.write(str);

            // Now close the writer
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
// Writer close() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Write the char to this writer
            // This will put the char in the writer
            // till it is printed on the console
            writer.write(65);

            // Now close the writer
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