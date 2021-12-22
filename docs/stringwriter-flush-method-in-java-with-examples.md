# Java 中的 StringWriter flush()方法，示例

> 原文:[https://www . geesforgeks . org/stringwriter-flush-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringwriter-flush-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的 **flush()** 方法用于刷新编写器。通过刷新编写器，这意味着清除编写器中可能存在也可能不存在的任何元素。它既不接受任何参数，也不返回值。

**语法:**

```
public void flush()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。它只会让作者脸红。

下面的程序说明了 flush()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// StringWriter flush() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // The string to be written in the writer
        String str = "GeeksForGeeks";

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Write the above string to this writer
            // This will put the string in the writer
            // till it is printed on the console
            writer.write(str);

            System.out.println(writer.toString());

            // Now clear the writer
            // using flush() method
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
// StringWriter flush() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Write the char to this writer
            // This will put the char in the writer
            // till it is printed on the console
            writer.write(65);

            System.out.println(writer.toString());

            // Now clear the writer
            // using flush() method
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
A

```