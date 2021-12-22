# Java 中 PrintWriter println(布尔)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print ln boolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/printwriter-printlnboolean-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printprintr-class-java-set-1/)** 类的 **println(布尔)**方法用于在流上打印指定的布尔值，然后换行。这个布尔值被作为一个参数。

**语法:**

```
public void println(boolean booleanValue)
```

**参数:**该方法接受一个强制参数**布尔值**，它是要写入流中的布尔值。

**返回值:**此方法不返回值。

下面的方法说明了 println(布尔)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintWriter println(boolean) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the boolean value 'true'
            // to this stream using println() method
            // This will put the booleanValue in the
            // stream till it is printed on the console
            printr.println(true);

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
true

```

**程序 2:**

```
// Java program to demonstrate
// PrintWriter println(boolean) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter printr
                = new PrintWriter(System.out);

            // Print the boolean value 'false'
            // to this stream using println() method
            // This will put the booleanValue in the
            // stream till it is printed on the console
            printr.println(false);

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
false

```