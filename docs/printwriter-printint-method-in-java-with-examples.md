# PrintWriter 用 Java 打印(int)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printint-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printprintr-class-java-set-1/)** 类的 **print(int)** 方法用于在流上打印指定的 int 值。这个 int 值被当作一个参数。

**语法:**

```java
public void print(int intValue)
```

**参数:**这个方法接受一个强制参数 **intValue** ，它是要写入流的 int 值。

**返回值:**此方法不返回值。

下面的方法说明了 print(int)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter print(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the int value '4'
            // to this stream using print() method
            // This will put the intValue in the
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
// PrintWriter print(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the int value '65'
            // to this stream using print() method
            // This will put the intValue in the
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