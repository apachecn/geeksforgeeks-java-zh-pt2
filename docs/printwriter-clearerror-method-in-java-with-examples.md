# Java 中的 PrintWriter clearError()方法，带示例

> 原文:[https://www . geesforgeks . org/print writer-clear error-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-clearerror-method-in-java-with-examples/)

Java 中类的 **clearError()** 方法用于清除这个 PrintWriter 实例的错误状态。它清除流中可能发生或没有发生的任何错误。因此，在这个方法之后，checkError()方法将总是返回 false。

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
// PrintWriter clearError() method

import java.io.*;

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

            // Create a PrintWriter instance
            GFG writer
                = new GFG(System.out);

            // Write the above string to this writer
            // This will put the string in the stream
            // till it is printed on the console
            writer.write(str);

            // Now clear the stream
            // using clearError() method
            writer.clearError();

            System.out.println("\nHas any error occurred: "
                               + writer.checkError());
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
// PrintWriter clearError() method

import java.io.*;

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

            // Create a PrintWriter instance
            GFG writer
                = new GFG(System.out);

            // Write the char to this writer
            // This will put the char in the stream
            // till it is printed on the console
            writer.write(65);

            // Now clear the stream
            // using clearError() method
            writer.clearError();

            System.out.println("\nHas any error occurred: "
                               + writer.checkError());
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