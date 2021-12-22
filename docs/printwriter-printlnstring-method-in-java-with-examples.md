# Java 中 PrintWriter println(字符串)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-printlnstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printlnstring-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的 **println(String)** 方法用于在流上打印指定的字符串，然后换行。该字符串被视为参数。

**语法:**

```
public void println(String string)
```

**参数:**此方法接受一个强制参数**字符串**，它是要在流中打印的字符串。

**返回值:**此方法不返回值。

下面的方法说明了 println(字符串)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintWriter println(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the String
            // to be printed in the stream
            String string = "GeeksForGeeks";

            // print the string
            // to this writer using print() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.println(string);

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
GeeksForGeeks

```

**程序 2:**

```
// Java program to demonstrate
// PrintWriter println(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the String
            // to be printed in the stream
            String string = "GFG";

            // print the string
            // to this writer using print() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.println(string);

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
GFG

```