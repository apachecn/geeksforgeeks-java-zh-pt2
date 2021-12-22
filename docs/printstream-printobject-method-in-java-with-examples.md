# Java 中的 PrintStream 打印(对象)方法，示例

> 原文:[https://www . geesforgeks . org/print stream-print object-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printstream-printobject-method-in-java-with-examples/)

Java 中 **[【打印流】](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** 类的**打印(对象)**方法用于打印流上指定的对象。该对象作为一个参数。

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
// PrintStream print(Object) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Get the char[] object
            // to be printed in the stream
            char[] object = { 'G', 'e', 'e', 'k', 's',
                              'F', 'o', 'r',
                              'G', 'e', 'e', 'k', 's' };

            // print the object
            // to this stream using print() method
            // This will put the object in the stream
            // till it is printed on the console
            stream.print(object);

            stream.flush();
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
// PrintStream print(Object) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintStream instance
            PrintStream stream
                = new PrintStream(System.out);

            // Get the String Object
            // to be printed in the stream
            String object = "GFG";

            // print the object
            // to this stream using print() method
            // This will put the object in the stream
            // till it is printed on the console
            stream.print(object);

            stream.flush();
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