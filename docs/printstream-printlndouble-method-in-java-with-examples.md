# Java 中的 PrintStream println(double)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-printlnddouble-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-printlndouble-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **println(double)** 方法，用于在流上打印指定的 double 值，然后换行。这个双精度值被作为一个参数。

**语法:**

```
public void println(double doubleValue)
```

**参数:**该方法接受一个强制参数**双值**，这是要写入流的双值。

**返回值:**此方法不返回值。

下面的方法说明了 println(双)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintStream println(double) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the double value '4.5'
            // to this stream using println() method
            // This will put the doubleValue in the
            // stream till it is printed on the console
            stream.println(4.5);

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
4.5

```

**程序 2:**

```
// Java program to demonstrate
// PrintStream println(double) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the double value '1.65'
            // to this stream using println() method
            // This will put the doubleValue in the
            // stream till it is printed on the console
            stream.println(1.65);

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