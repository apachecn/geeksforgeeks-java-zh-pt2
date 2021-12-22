# Java 中的 PrintStream println()方法，示例

> 原文:[https://www . geesforgeks . org/print stream-println-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-println-method-in-java-with-examples/)

Java 中 **[PrintStream](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **println()** 方法用来打断流中的线。此方法不接受任何参数或返回任何值。

**语法:**

```
public void println()
```

**参数:**该方法不接受任何参数。

**返回:**此方法不返回任何值。

下面的方法说明了 println()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintStream println() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the value 'GFG'
            // to this stream using print() method
            // This will put the  in the
            // stream till it is printed on the console
            stream.print("GFG");

            // Break the line in the stream
            // using println() method
            stream.println();

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

**程序 2:**

```
// Java program to demonstrate
// PrintStream println() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the  value '1.65'
            // to this stream using print() method
            // This will put the  in the
            // stream till it is printed on the console
            stream.print(1.65);

            // Break the line in the stream
            // using println() method
            stream.println();

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
1.65

```