# Java 中的 PrintStream 打印(String)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-print string-in-Java-method-with-examples/](https://www.geeksforgeeks.org/printstream-printstring-method-in-java-with-examples/)

Java 中 **[PrintStream](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **print(String)** 方法用于在流上打印指定的 String 值。该字符串值被视为参数。

**语法:**

```
public void print(String StringValue)
```

**参数:**该方法接受一个强制参数**字符串值**，它是要写入流的字符串值。

**返回值:**此方法不返回值。

以下方法说明了打印(字符串)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintStream print(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the String value 'GeeksForGeeks'
            // to this stream using print() method
            // This will put the StringValue in the
            // stream till it is printed on the console
            stream.print("GeeksForGeeks");

            stream.flush();
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
// PrintStream print(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the String value 'GFG'
            // to this stream using print() method
            // This will put the StringValue in the
            // stream till it is printed on the console
            stream.print("GFG");

            stream.flush();
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