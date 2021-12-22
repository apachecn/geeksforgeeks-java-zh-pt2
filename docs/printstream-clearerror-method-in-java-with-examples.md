# Java 中的 PrintStream clearError()方法，带示例

> 原文:[https://www . geesforgeks . org/print stream-clear error-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-clearerror-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的 **clearError()** 方法用来清除这个打印流实例的错误状态。它清除流中可能发生或没有发生的任何错误。因此，在这个方法之后，checkError()方法将总是返回 false。

**语法:**

```
protected void clearError()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。

下面的方法说明了 clearError()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintStream clearError() method

import java.io.*;

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

            // Create a PrintStream instance
            GFG stream
                = new GFG(System.out);

            // Write the above string to this stream
            // This will put the string in the stream
            // till it is printed on the console
            stream.print(str);

            // Now clear the stream
            // using clearError() method
            stream.clearError();

            System.out.println("\nHas any error occurred: "
                               + stream.checkError());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
GeeksForGeeks
Has any error occurred: false

```

**程序 2:**

```
// Java program to demonstrate
// PrintStream clearError() method

import java.io.*;

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

            // Create a PrintStream instance
            GFG stream
                = new GFG(System.out);

            // Write the char to this stream
            // This will put the char in the stream
            // till it is printed on the console
            stream.write(65);

            // Now clear the stream
            // using clearError() method
            stream.clearError();

            System.out.println("\nHas any error occurred: "
                               + stream.checkError());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
A
Has any error occurred: false

```