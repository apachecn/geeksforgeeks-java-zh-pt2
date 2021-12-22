# Java 中的 PrintStream flush()方法，示例

> 原文:[https://www . geesforgeks . org/print stream-flush-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-flush-method-in-java-with-examples/)

Java 中 **[PrintStream](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **flush()** 方法用于冲洗该流。通过冲洗流，这意味着清除流中可能存在或可能不存在的任何元素。它既不接受任何参数，也不返回值。

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
// PrintStream flush() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // The string to be written in the Stream
        String str = "GeeksForGeeks";

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Write the above string to this stream
            // This will put the string in the stream
            // till it is printed on the console
            stream.print(str);

            // Now clear the stream
            // using flush() method
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
// PrintStream flush() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Write the char to this stream
            // This will put the char in the stream
            // till it is printed on the console
            stream.write(65);

            // Now clear the stream
            // using flush() method
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
A

```