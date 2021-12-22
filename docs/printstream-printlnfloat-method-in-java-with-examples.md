# Java 中的 PrintStream println(float)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-print infoat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-printlnfloat-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **println(float)** 方法是将指定的 float 值打印在流上，然后换行。这个浮点值被当作一个参数。

**语法:**

```java
public void println(float floatValue)
```

**参数:**该方法接受一个强制参数**浮点值**，即要写入流的浮点值。

**返回值:**此方法不返回值。

下面的方法说明了 println(float)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintStream println(float) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream printr
                = new PrintStream(System.out);

            // Print the float value '4.5'
            // to this stream using println() method
            // This will put the floatValue in the
            // stream till it is printed on the console
            printr.println(4.5);

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
// PrintStream println(float) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream printr
                = new PrintStream(System.out);

            // Print the float value '1.65'
            // to this stream using println() method
            // This will put the floatValue in the
            // stream till it is printed on the console
            printr.println(1.65);

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