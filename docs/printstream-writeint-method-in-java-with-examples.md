# Java 中的 PrintStream write(int)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-writeint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-writeint-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **write(int)** 方法用于在流上写入指定的字节值。该字节值是使用作为整数值传递的字节值的 ASCII 值指定的。该整数值被作为参数。

**语法:**

```java
public void write(int ascii)
```

**参数:**该方法接受一个强制参数 **ascii** ，它是要写入流的字节值的 ascii 值。

**返回值:**此方法不返回值。

下面的方法说明了 write(int)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintStream write(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Write the byte value '0' to this stream
            // using write() method
            // This will put the string in the stream
            // till it is printed on the console
            stream.write(48);

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
0

```

**程序 2:**

```java
// Java program to demonstrate
// PrintStream write(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Write the byte value 'A' to this stream
            // using write() method
            // This will put the string in the stream
            // till it is printed on the console
            stream.write(65);

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