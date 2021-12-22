# 用 Java 打印流打印(长)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-print long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-printlong-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的**打印(长)**方法用于在流上打印指定的长值。这个长值被当作一个参数。

**语法:**

```java
public void print(long longValue)
```

**参数:**该方法接受一个强制参数**长值**，它是要写入流的长值。

**返回值:**此方法不返回值。

下面的方法说明了打印(长)的工作方法:

**程序 1:**

```java
// Java program to demonstrate
// PrintStream print(long) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the long value '4'
            // to this stream using print() method
            // This will put the longValue in the
            // stream till it is printed on the console
            stream.print(4);

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
4

```

**程序 2:**

```java
// Java program to demonstrate
// PrintStream print(long) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Print the long value '65'
            // to this stream using print() method
            // This will put the longValue in the
            // stream till it is printed on the console
            stream.print(65);

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
65

```