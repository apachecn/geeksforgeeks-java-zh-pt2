# 用示例在 Java 中编写器追加(char)方法

> 原文:[https://www . geesforgeks . org/writer-append char-method-in-Java-with-examples/](https://www.geeksforgeeks.org/writer-appendchar-method-in-java-with-examples/)

Java 中 **Writer** 类的**追加(char)** 方法用于在 Writer 上追加指定的 char 值。这个字符值被作为一个参数。

**语法:**

```
public void append(char charValue)
```

**参数:**该方法接受一个强制参数**字符值**，它是要附加到编写器上的字符值。

**返回值:**此方法不返回值。

下面的方法说明了 append(char)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// Writer append(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Append the char value 'A'
            // to this writer using append() method
            // This will put the charValue in the
            // writer till it is appended on the console
            writer.append('A');

            writer.flush();
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

**程序 2:**

```
// Java program to demonstrate
// Writer append(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Append the char value 'G'
            // to this writer using append() method
            // This will put the charValue in the
            // writer till it is appended on the console
            writer.append('G');

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
G

```