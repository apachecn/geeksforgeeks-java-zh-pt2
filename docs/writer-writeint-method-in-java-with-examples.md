# 用示例用 Java 编写 Writer(int)方法

> 原文:[https://www . geesforgeks . org/writer-writeint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/writer-writeint-method-in-java-with-examples/)

Java 中类的 **write(int)** 方法用于在 Writer 上写入指定的字节值。该字节值是使用作为整数值传递的字节值的 ASCII 值指定的。该整数值被作为参数。

**语法:**

```java
public void write(int ascii)
```

**参数:**该方法接受一个强制参数 **ascii** ，它是要写入写入器的字节值的 ascii 值。

**返回值:**此方法不返回值。

下面的方法说明了 write(int)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// Writer write(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Write the byte value '0' to this writer
            // using write() method
            // This will put the string in the writer
            // till it is printed on the console
            writer.write(48);

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
0

```

**程序 2:**

```java
// Java program to demonstrate
// Writer write(int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Write the byte value 'A' to this writer
            // using write() method
            // This will put the string in the writer
            // till it is printed on the console
            writer.write(65);

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
A

```