# Java 中 PrintWriter println(长)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print lnlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printlnlong-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printprintr-class-java-set-1/)** 类的 **println(long)** 方法是将指定的 long 值打印在流上，然后换行。这个长值被当作一个参数。

**语法:**

```java
public void println(long longValue)
```

**参数:**该方法接受一个强制参数**长值**，它是要写入流的长值。

**返回值:**此方法不返回值。

下面的方法说明了 println(long)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter println(long) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the long value '4'
            // to this stream using println() method
            // This will put the longValue in the
            // stream till it is printed on the console
            printr.println(4);

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
// PrintWriter println(long) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the long value '65'
            // to this stream using println() method
            // This will put the longValue in the
            // stream till it is printed on the console
            printr.println(65);

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