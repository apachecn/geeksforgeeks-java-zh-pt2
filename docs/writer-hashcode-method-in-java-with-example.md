# 用示例编写 Java 中的 hashCode()方法

> 原文:[https://www . geesforgeks . org/writer-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/writer-hashcode-method-in-java-with-example/)

Java 中类的 **hashCode()** 方法用来获取这个 Writer 实例的 hashCode 值。此方法不接受任何参数，并返回所需的 int 值。

**语法:**

> public int hashCode()

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回**一个 int 值**，它是 Writer 实例的 HashCode 值。

下面的方法说明了 hashCode()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// Writer hashCode() method

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

            // Write the string
            // to this writer using write() method
            writer.write(string);

            // Get the HashCode value using hashCode()
            System.out.println("HashCode value: "
                               + writer.hashCode());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
HashCode value: 589431969

```

**程序 2:**

```
// Java program to demonstrate
// Writer hashCode() method

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
            String string = "GFG";

            // Write the string
            // to this writer using write() method
            writer.write(string);

            // Get the HashCode value using hashCode()
            System.out.println("HashCode value: "
                               + writer.hashCode());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
HashCode value: 589431969

```