# Java 中的 StringWriter getClass()方法，带示例

> 原文:[https://www . geesforgeks . org/stringwriter-getclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringwriter-getclass-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的 **getClass()** 方法用来获取这个 StringWriter 实例的父类。此方法不接受任何参数，并返回所需的类详细信息。

**语法:**

> 公共最终类字符串 getClass()

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回**类细节**，它是 StringWriter 实例的父类。

下面的方法说明了 getClass()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// StringWriter getClass() method

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

            // Get Class details using getClass()
            System.out.println("Parent Class: "
                               + writer.getClass());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Parent Class: class java.io.StringWriter

```

**程序 2:**

```java
// Java program to demonstrate
// StringWriter getClass() method

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

            // Get Class details using getClass()
            System.out.println("Parent Class: "
                               + writer.getClass());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Parent Class: class java.io.StringWriter

```