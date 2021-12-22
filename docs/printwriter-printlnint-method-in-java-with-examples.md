# Java 中 PrintWriter println(int)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-printlint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printlnint-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printprintr-class-java-set-1/)** 类的 **println(int)** 方法是将指定的 int 值打印在流上，然后换行。这个 int 值被当作一个参数。

**语法:**

```
public void println(int intValue)
```

**参数:**这个方法接受一个强制参数 **intValue** ，它是要写入流的 int 值。

**返回值:**此方法不返回值。

下面的方法说明了 println(int)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintWriter println(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the int value '4'
            // to this stream using println() method
            // This will put the intValue in the
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

```
4

```

**程序 2:**

```
// Java program to demonstrate
// PrintWriter println(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the int value '65'
            // to this stream using println() method
            // This will put the intValue in the
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

```
65

```