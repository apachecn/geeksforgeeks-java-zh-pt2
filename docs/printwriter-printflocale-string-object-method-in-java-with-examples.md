# Java 中 printwister printf(Locale，String，Object)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print flocale-string-object-in-Java-method-with-examples/](https://www.geeksforgeeks.org/printwriter-printflocale-string-object-method-in-java-with-examples/)

Java 中类的 **printf(Locale，String，Object)** 方法用于使用给定的 **Locale** 打印流中的格式化字符串。字符串使用指定的**格式**和作为参数传递的**参数**进行格式化。

**语法:**

> public PrintWriter printf(本地、字符串格式、对象... args)

**参数:**该方法接受两个强制参数:

*   **区域设置**是应用于该方法的区域设置值
*   **格式**是字符串的格式。
*   **参数**是格式化字符串的参数数量。它可以是可选的，即根据格式没有参数或任意数量的参数。

**返回值:**这个方法返回这个 PrintWriter 实例。

**异常:**该方法抛出以下异常:

*   **NullPointRexception**如果格式为空，则抛出此异常。
*   **IllegalFormatException** 如果指定的格式不合法或参数不足，则会引发此问题。

下面的方法说明了 printf(区域设置、字符串、对象)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter printf(String, Object) method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Get the parameters
            Locale locale = Locale.getDefault();

            double arg = 47.65734;

            String format = "GeeksForGeeks %.8f";

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // print the formatted string
            // to this writer using printf() method
            writer.printf(format, arg);

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
GeeksForGeeks 47.65734000

```

**程序 2:**

```java
// Java program to demonstrate
// PrintWriter printf(String, Object) method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Get the parameters
            Locale locale = Locale.getDefault();

            String arg1 = "GFG";
            String arg2 = "GeeksforGeeks";

            String format = "A Computer Science "
                            + "Portal  %1$s, %1$s and %2$s";

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // print the formatted string
            // to this writer using printf() method
            writer.printf(format, arg1, arg2);

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
A Computer Science Portal  GFG, GFG and GeeksforGeeks

```