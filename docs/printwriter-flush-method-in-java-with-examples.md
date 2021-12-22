# Java 中 PrintWriter flush()方法，示例

> 原文:[https://www . geesforgeks . org/print writer-flush-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-flush-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的 **flush()** 方法用于冲刷溪流。通过冲洗流，这意味着清除流中可能存在或可能不存在的任何元素。它既不接受任何参数，也不返回值。

**语法:**

```java
public void flush()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。它只是冲向溪流。

下面的方法说明了 flush()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter flush() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // The string to be written in the Writer
        String str = "GeeksForGeeks";

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the above string to this writer
            // This will put the string in the stream
            // till it is printed on the console
            writer.write(str);

            // Now clear the stream
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
// PrintWriter flush() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the char to this writer
            // This will put the char in the stream
            // till it is printed on the console
            writer.write(65);

            // Now clear the stream
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