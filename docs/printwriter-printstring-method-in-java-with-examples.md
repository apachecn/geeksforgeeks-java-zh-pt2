# PrintWriter 用 Java 打印(字符串)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print string-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printstring-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的 **print(String)** 方法用于在流上打印指定的 String 值。该字符串值被视为参数。

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
// PrintWriter print(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Print the String value 'GeeksForGeeks'
            // to this stream using print() method
            // This will put the StringValue in the
            // stream till it is printed on the console
            writer.print("GeeksForGeeks");

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
// PrintWriter print(String) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Print the String value 'GFG'
            // to this stream using print() method
            // This will put the StringValue in the
            // stream till it is printed on the console
            writer.print("GFG");

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