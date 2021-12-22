# PrintWriter 用 Java 打印(长)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printlong-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printprintr-class-java-set-1/)** 类的 **print(long)** 方法用于在流上打印指定的 long 值。这个长值被当作一个参数。该方法类似于**write(String.valueOf(long))**，其中 string . value of(long)返回字节数，这些字节在 write()方法的帮助下被写入流。

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
// PrintWriter print(long) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the long value '4'
            // to this stream using print() method
            // This will put the longValue in the
            // stream till it is printed on the console
            printr.print(4);

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
4

```

**程序 2:**

```java
// Java program to demonstrate
// PrintWriter print(long) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the long value '65'
            // to this stream using print() method
            // This will put the longValue in the
            // stream till it is printed on the console
            printr.print(65);

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
65

```