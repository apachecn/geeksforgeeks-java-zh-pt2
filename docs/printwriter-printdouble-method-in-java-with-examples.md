# PrintWriter 用 Java 打印(双)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print double-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printdouble-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printprintr-class-java-set-1/)** 类的 **print(double)** 方法用于在流上打印指定的 double 值。这个双精度值被作为一个参数。

**语法:**

```java
public void print(double doubleValue)
```

**参数:**该方法接受一个强制参数**双值**，这是要写入流的双值。

**返回值:**此方法不返回值。

下面的方法说明了打印(双)的工作方法:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter print(double) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the double value '4.5'
            // to this stream using print() method
            // This will put the doubleValue in the
            // stream till it is printed on the console
            printr.print(4.5);

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
4.5

```

**程序 2:**

```java
// Java program to demonstrate
// PrintWriter print(double) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the double value '1.65'
            // to this stream using print() method
            // This will put the doubleValue in the
            // stream till it is printed on the console
            printr.print(1.65);

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
1.65

```