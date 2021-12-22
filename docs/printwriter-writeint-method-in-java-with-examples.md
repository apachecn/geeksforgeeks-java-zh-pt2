# PrintWriter 用 Java 写(int)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-writeint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-writeint-method-in-java-with-examples/)

Java 中**[【PrintWriter】](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)**类的 **write(int)** 方法用于在流中写入指定的字符。该字符是使用作为整数值传递的字符的 ASCII 值指定的。该整数值被作为参数。

**语法:**

```java
public void write(int ascii)
```

**参数:**该方法接受一个强制参数 **ascii** ，它是要写入流中的字符的 ascii 值。

**返回值:**此方法不返回值。

下面的方法说明了 write(int)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter write(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the character '0' to this writer
            // using write() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.write(48);

            writer.flush();
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
// PrintWriter write(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Write the character 'A' to this writer
            // using write() method
            // This will put the string in the stream
            // till it is printed on the console
            writer.write(65);

            writer.flush();
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