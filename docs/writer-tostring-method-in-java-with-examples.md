# 用示例编写 Java 中的 toString()方法

> 原文:[https://www . geesforgeks . org/writer-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/writer-tostring-method-in-java-with-examples/)

Java 中 **[Writer](https://www.geeksforgeeks.org/java-io-writer-class-java/)** 类的 **toString()** 方法用来获取这个 Writer 实例的字符串表示。此方法不接受任何参数，并返回所需的字符串值。

**语法:**

> 公共字符串 toString()

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回**一个字符串值**，它是 Writer 实例的字符串表示。

下面的方法说明了 toString()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// Writer toString() method

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

            // Write the the string
            // to this writer using write() method
            writer.write(string);

            System.out.println("String representation: "
                               + writer.toString());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
String representation: java.io.PrintWriter@232204a1

```

**程序 2:**

```java
// Java program to demonstrate
// Writer toString() method

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

            // Write the the string
            // to this writer using write() method
            writer.write(string);

            System.out.println("String representation: "
                               + writer.toString());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
String representation: java.io.PrintWriter@232204a1

```