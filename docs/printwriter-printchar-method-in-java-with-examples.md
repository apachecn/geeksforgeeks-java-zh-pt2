# PrintWriter 用 Java 打印(char)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print char-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printchar-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printprintr-class-java-set-1/)** 类的**打印(char)** 方法用于在流上打印指定的 char 值。这个字符值被作为一个参数。

**语法:**

```java
public void print(char charValue)
```

**参数:**该方法接受一个强制参数 **charValue** ，即要写入流的 char 值。

**返回值:**此方法不返回值。

下面的方法说明了打印(char)的工作方法:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter print(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the char value 'A'
            // to this stream using print() method
            // This will put the charValue in the
            // stream till it is printed on the console
            printr.print('A');

            printr.flush();
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

**程序 2:**

```java
// Java program to demonstrate
// PrintWriter print(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the char value 'G'
            // to this stream using print() method
            // This will put the charValue in the
            // stream till it is printed on the console
            printr.print('G');

            printr.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
G

```