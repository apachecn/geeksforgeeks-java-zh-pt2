# Java 中的 PrintStream setError()方法，示例

> 原文:[https://www . geesforgeks . org/print stream-set error-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-seterror-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **setError()** 方法用来设置这个打印流实例的错误状态。此方法用作指示符，指示流中发生了错误。它是受保护的，因此需要通过派生 PrintStream 类来使用它来实现。

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
// PrintStream setError() method

import java.io.*;

// extending the PrintStream Class
class GFG extends PrintStream {

    // Defining the protected constructor
    public GFG(OutputStream out)
    {
        super(System.out);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // The string to be written in the Stream
        String str = "GeeksForGeeks";

        try {

            // Create a GFG instance
            GFG stream
                = new GFG(System.out);

            // Write the above string to this stream
            // This will put the string in the stream
            // till it is printed on the console
            stream.print(str);

            stream.flush();

            // Use the protected setError() method
            stream.setError();
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
// PrintStream setError() method

import java.io.*;

// extending the PrintStream Class
class GFG extends PrintStream {

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
            GFG stream
                = new GFG(System.out);

            // Write the char to this stream
            // This will put the char in the stream
            // till it is printed on the console
            stream.write(65);

            stream.flush();

            // Use the protected setError() method
            stream.setError();
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