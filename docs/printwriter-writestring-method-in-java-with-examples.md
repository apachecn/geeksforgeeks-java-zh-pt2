# PrintWriter 用 Java 写(String)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-write string-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-writestring-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的 **write(String)** 方法用于在流上写入指定的字符串。该字符串值被视为参数。

**语法:**

```java
public void write(String string)
```

**参数:**该方法接受一个强制参数**字符串**，它是要写入流中的字符串。

**返回值:**此方法不返回值。

下面的方法说明了 write(String)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter write(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the String 'GeeksForGeeks'
            // to this writer using write() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.write("GeeksForGeeks");

            writer.flush();
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
// PrintWriter write(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the String 'GFG'
            // to this writer using write() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.write("GFG");

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
GFG

```