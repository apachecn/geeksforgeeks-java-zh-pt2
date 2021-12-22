# 用示例编写 Java 中的 getClass()方法

> 原文:[https://www . geesforgeks . org/writer-getclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/writer-getclass-method-in-java-with-examples/)

Java 中 **getClass()** 方法 **[Writer](https://www.geeksforgeeks.org/java-io-writer-class-java/)** 类用来获取这个 Writer 实例的父类。此方法不接受任何参数，并返回所需的类详细信息。

**语法:**

> 公共最终类字符串 getClass()

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回**类细节**，它是 Writer 实例的父类。

下面的方法说明了 getClass()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// Writer getClass() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Get the String
            // to be written in the stream
            String string = "GeeksForGeeks";

            // Write the the string
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

```
Parent Class: class java.io.PrintWriter

```

**程序 2:**

```
// Java program to demonstrate
// Writer getClass() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new OutputStreamWriter(System.out);

            // Get the String
            // to be written in the stream
            String string = "GFG";

            // Write the the string
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

```
Parent Class: class java.io.OutputStreamWriter

```