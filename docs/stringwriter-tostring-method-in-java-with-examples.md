# Java 中的 StringWriter toString()方法，带示例

> 原文:[https://www . geesforgeks . org/stringwriter-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringwriter-tostring-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的 **toString()** 方法用来获取这个 StringWriter 实例的字符串表示。此方法不接受任何参数，并返回所需的字符串值。

**语法:**

```java
public String toString()
```

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回**一个字符串值**，它是 StringWriter 实例的字符串表示。

下面的方法说明了 toString()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// StringWriter toString() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Get the String
            // to be written in the stream
            String string = "GeeksForGeeks";

            // Write the string
            // to this writer using write() method
            writer.write(string);

            System.out.println("String representation: "
                               + writer.toString());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
String representation: GeeksForGeeks

```

**程序 2:**

```java
// Java program to demonstrate
// StringWriter toString() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Get the String
            // to be written in the stream
            String string = "GFG";

            // Write the string
            // to this writer using write() method
            writer.write(string);

            System.out.println("String representation: "
                               + writer.toString());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
String representation: GFG

```