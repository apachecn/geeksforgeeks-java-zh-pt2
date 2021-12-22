# PrintWriter 用 Java 追加(CharSequence)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-appendcharsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-appendcharsequence-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的 **append(CharSequence)** 方法用于在流中写入指定的 CharSequence。这个字符序列值被作为一个参数。

**语法:**

```java
public PrintWriter append(CharSequence charSequence)
```

**参数:**该方法接受一个强制参数**字符序列**，它是要写入流中的字符序列。

**返回值:**这个方法返回这个 PrintWriter 实例。

下面的方法说明了 append(CharSequence)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter append(CharSequence) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the CharSequence 'GeeksForGeeks'
            // to this writer using append() method
            // This will put the charSequence in the stream
            // till it is printed on the console
            writer.append("GeeksForGeeks");

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
// PrintWriter append(CharSequence) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the CharSequence 'GFG'
            // to this writer using append() method
            // This will put the charSequence in the stream
            // till it is printed on the console
            writer.append("GFG");

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