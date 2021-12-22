# PrintWriter 用 Java 打印(浮点)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print float-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printfloat-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printprintr-class-java-set-1/)** 类的 **print(float)** 方法用于在流上打印指定的 float 值。这个浮点值被当作一个参数。

**语法:**

```java
public void print(float floatValue)
```

**参数:**该方法接受一个强制参数**浮点值**，即要写入流的浮点值。

**返回值:**此方法不返回值。

下面的方法说明了打印(浮动)的工作方法:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter print(float) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the float value '4.5'
            // to this stream using print() method
            // This will put the floatValue in the
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
// PrintWriter print(float) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the float value '1.65'
            // to this stream using print() method
            // This will put the floatValue in the
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