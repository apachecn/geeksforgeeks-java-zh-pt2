# Java 中 PrintWriter setError()方法，带示例

> 原文:[https://www . geesforgeks . org/print writer-set error-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-seterror-method-in-java-with-examples/)

Java 中类的 **setError()** 方法用来设置这个 PrintWriter 实例的错误状态。此方法用作指示符，指示流中发生了错误。它是受保护的，因此需要通过派生 PrintWriter 类来使用它来实现。

**语法:**

```java
protected void setError()
```

**参数:**该方法不接受任何参数。

**返回值:**这个方法不返回任何东西。

下面的方法说明了 setError()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter setError() method

import java.io.*;

// extending the PrintWriter Class
class GFG extends PrintWriter {

    // Defining the protected constructor
    public GFG(OutputStream out)
    {
        super(System.out);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // The string to be written in the Writer
        String str = "GeeksForGeeks";

        try {

            // Create a GFG instance
            GFG writer
                = new GFG(System.out);

            // Write the above string to this writer
            // This will put the string in the stream
            // till it is printed on the console
            writer.write(str);

            writer.flush();

            // Use the protected setError() method
            writer.setError();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
GeeksForGeeks

```

**程序 2:**

```java
// Java program to demonstrate
// PrintWriter setError() method

import java.io.*;

// extending the PrintWriter Class
class GFG extends PrintWriter {

    // Defining the protected constructor
    public GFG(OutputStream out)
    {
        super(System.out);
    }

    // Driver Code
    public static void main(String[] args)
    {

        try {

            // Create a GFG instance
            GFG writer
                = new GFG(System.out);

            // Write the char to this writer
            // This will put the char in the stream
            // till it is printed on the console
            writer.write(65);

            writer.flush();

            // Use the protected setError() method
            writer.setError();
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