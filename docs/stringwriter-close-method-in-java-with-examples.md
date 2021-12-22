# Java 中的 StringWriter close()方法，示例

> 原文:[https://www . geesforgeks . org/stringwriter-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringwriter-close-method-in-java-with-examples/)

Java 中的 **close()** 方法 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类用于关闭 Writer。关闭编写器会释放其中的任何值或与之关联的任何资源。StringWriter 实例一旦关闭就不起作用了。同样，StringWriter 实例一旦关闭就不能再次关闭。

**语法:**

```java
public void close()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。它只是关闭了流。

下面的程序说明了 close()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// StringWriter close() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // The string to be written in the Stream
        String str = "GeeksForGeeks";

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Write the above string to this writer
            // This will put the string in the writer
            // till it is printed on the console
            writer.write(str);

            System.out.println(writer.toString());

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

```java
GeeksForGeeks

```

**程序 2:**

```java
// Java program to demonstrate
// StringWriter close() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Write the char to this writer
            // This will put the char in the writer
            // till it is printed on the console
            writer.write(65);

            System.out.println(writer.toString());

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

```java
A

```