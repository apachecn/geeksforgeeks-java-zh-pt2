# Java 中的 PrintWriter checkError()方法，带示例

> 原文:[https://www . geesforgeks . org/print writer-checker err-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-checkerror-method-in-java-with-examples/)

Java 中类的 **checkError()** 方法用于检查这个 PrintWriter 实例的错误状态。此方法刷新流以检查错误状态。它返回一个布尔值，告知流是否遇到任何错误。

**语法:**

```java
public boolean checkError()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**布尔值**，说明流是否遇到任何错误。如果遇到任何错误，它将返回 true。否则返回假。

下面的方法说明了 checkError()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter checkError() method

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

            // Now check the stream
            // using checkError() method
            System.out.println("\nHas any error occurred: "
                               + writer.checkError());
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
Has any error occurred: false

```

**程序 2:**

```java
// Java program to demonstrate
// PrintWriter checkError() method

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

            // Now check the stream
            // using checkError() method
            System.out.println("\nHas any error occurred: "
                               + writer.checkError());
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
Has any error occurred: false

```