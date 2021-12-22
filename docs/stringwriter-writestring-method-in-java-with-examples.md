# StringWriter 用 Java 写(String)方法，示例

> 原文:[https://www . geesforgeks . org/stringwriter-write string-in-Java-method-with-examples/](https://www.geeksforgeeks.org/stringwriter-writestring-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的 **write(String)** 方法用于在流上写入指定的字符串。该字符串值被视为参数。

**语法:**

```
public void write(String string)
```

**参数:**该方法接受一个强制参数**字符串**，它是要写入流中的字符串。

**返回值:**此方法不返回值。

下面的程序说明了写(字符串)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// StringWriter write(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Write the String 'GeeksForGeeks'
            // to this writer using write() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.write("GeeksForGeeks");

            System.out.println(writer.toString());
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
// StringWriter write(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Write the String 'GFG'
            // to this writer using write() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.write("GFG");

            System.out.println(writer.toString());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
GFG

```