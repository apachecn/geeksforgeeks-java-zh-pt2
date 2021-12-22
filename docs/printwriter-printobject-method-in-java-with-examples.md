# PrintWriter 用 Java 打印(对象)方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print object-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-printobject-method-in-java-with-examples/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的 **print(Object)** 方法用于打印流中指定的对象。该对象作为一个参数。

**语法:**

```
public void print(Object object)
```

**参数:**此方法接受一个强制参数**对象**，它是要在流中打印的对象。

**返回值:**此方法不返回值。

以下方法说明了打印(对象)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintWriter print(Object) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the char[] object
            // to be printed in the stream
            char[] object = { 'G', 'e', 'e', 'k', 's',
                              'F', 'o', 'r',
                              'G', 'e', 'e', 'k', 's' };

            // print the object
            // to this writer using print() method
            // This will put the object in the stream
            // till it is printed on the console
            writer.print(object);

            writer.flush();
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

```

**程序 2:**

```
// Java program to demonstrate
// PrintWriter print(Object) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the String Object
            // to be printed in the stream
            String object = "GFG";

            // print the object
            // to this writer using print() method
            // This will put the object in the stream
            // till it is printed on the console
            writer.print(object);

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
GFG

```