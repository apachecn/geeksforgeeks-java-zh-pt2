# Java 中的打印流追加(CharSequence)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-appendcharsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-appendcharsequence-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的**追加(CharSequence)** 方法用于在流上写入指定的 CharSequence。这个字符序列值被作为一个参数。

**语法:**

```java
public PrintStream append(CharSequence charSequence)
```

**参数:**该方法接受一个强制参数**字符序列**，它是要写入流中的字符序列。

**返回值:**这个方法返回这个 PrintStream 实例。

下面的方法说明了 append(CharSequence)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintStream append(CharSequence) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Write the CharSequence 'GeeksForGeeks'
            // to this stream using append() method
            // This will put the charSequence in the stream
            // till it is printed on the console
            stream.append("GeeksForGeeks");

            stream.flush();
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
// PrintStream append(CharSequence) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Write the CharSequence 'GFG'
            // to this stream using append() method
            // This will put the charSequence in the stream
            // till it is printed on the console
            stream.append("GFG");

            stream.flush();
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