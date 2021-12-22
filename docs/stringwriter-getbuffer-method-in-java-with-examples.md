# Java 中 StringWriter getBuffer()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringwriter-get buffer-in-Java-method-with-examples/](https://www.geeksforgeeks.org/stringwriter-getbuffer-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的 **getBuffer()** 方法用于获取这个 StringWriter 实例的 [StringBuffer](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) 表示。该方法不接受任何参数，返回所需的 [StringBuffer](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) 值。

**语法:**

```java
public StringBuffer getBuffer()
```

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回**一个 [StringBuffer](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) 值**，它是 StringWriter 实例的 StringBuffer 表示。

下面的方法说明了 getBuffer()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// StringWriter getBuffer() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Get the String
            // to be written in the stream
            String string = "GeeksForGeeks";

            // Write the the string
            // to this writer using write() method
            writer.write(string);

            // Get the StringBuffer of this StringWriter
            StringBuffer stringBuffer = writer.getBuffer();

            System.out.println("StringBuffer representation: "
                               + stringBuffer);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
StringBuffer representation: GeeksForGeeks

```

**程序 2:**

```java
// Java program to demonstrate
// StringWriter getBuffer() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Get the String
            // to be written in the stream
            String string = "GFG";

            // Write the the string
            // to this writer using write() method
            writer.write(string);

            // Get the StringBuffer of this StringWriter
            StringBuffer stringBuffer = writer.getBuffer();

            System.out.println("StringBuffer representation: "
                               + stringBuffer);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
StringBuffer representation: GFG

```