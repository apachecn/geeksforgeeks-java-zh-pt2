# Java 中的 PrintStream println(布尔)方法，示例

> 原文:[https://www . geeksforgeeks . org/print stream-println boolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/printstream-printlnboolean-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **println(布尔)**方法用于打印流上指定的布尔值，然后换行。这个布尔值被作为一个参数。

**语法:**

```java
public void println(boolean booleanValue)
```

**参数:**该方法接受一个强制参数**布尔值**，它是要写入流中的布尔值。

**返回值:**此方法不返回值。

下面的方法说明了 println(布尔)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintStream println(boolean) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the boolean value 'true'
            // to this stream using println() method
            // This will put the booleanValue in the
            // stream till it is printed on the console
            stream.println(true);

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
true

```

**程序 2:**

```java
// Java program to demonstrate
// PrintStream println(boolean) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the boolean value 'false'
            // to this stream using println() method
            // This will put the booleanValue in the
            // stream till it is printed on the console
            stream.println(false);

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
false

```