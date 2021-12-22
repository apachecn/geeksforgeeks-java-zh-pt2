# Java 中的 PrintStream 打印(char[])方法，示例

> 原文:[https://www . geesforgeks . org/print stream-print char-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-printchar-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的**打印(char[])** 方法用于打印流上指定的字符数组。这个字符数组作为一个参数。

**语法:**

```java
public void print(char[] charArray)
```

**参数:**该方法接受一个强制参数**字符数组**，它是要在流中打印的字符数组。

**返回值:**此方法不返回值。

**异常:**如果指定的 charArray()为空，此方法返回**空指针异常**。

下面的方法说明了 print(char[])方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintStream print(char[]) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Get the character array
            // to be printed in the stream
            char[] charArray = { 'G', 'e', 'e', 'k', 's',
                                 'F', 'o', 'r',
                                 'G', 'e', 'e', 'k', 's' };

            // print the charArray
            // to this stream using print() method
            // This will put the charArray in the stream
            // till it is printed on the console
            stream.print(charArray);

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
GeeksForGeeks

```

**程序 2:**

```java
// Java program to demonstrate
// PrintStream print(char[]) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Get the character array
            // to be printed in the stream
            char[] charArray = { 'G', 'F', 'G' };

            // print the charArray
            // to this stream using print() method
            // This will put the charArray in the stream
            // till it is printed on the console
            stream.print(charArray);

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
GFG

```