# Java 中 Writer flush()方法，示例

> 原文:[https://www . geeksforgeeks . org/writer-flush-in-Java-method-with-examples/](https://www.geeksforgeeks.org/writer-flush-method-in-java-with-examples/)

Java 中 **[Writer](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的**同花顺()**方法用于同花顺 Writer。通过刷新编写器，这意味着清除编写器中可能存在也可能不存在的任何元素。它既不接受任何参数，也不返回值。

**语法:**

```java
public void flush()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。它只会让作者脸红。

下面的方法说明了 flush()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// Writer flush() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // The string to be written in the writer
        String str = "GeeksForGeeks";

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Write the above string to this writer
            // This will put the string in the writer
            // till it is printed on the console
            writer.write(str);

            // Now clear the writer
            // using flush() method
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
// Writer flush() method

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

            // Now clear the writer
            // using flush() method
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
A

```