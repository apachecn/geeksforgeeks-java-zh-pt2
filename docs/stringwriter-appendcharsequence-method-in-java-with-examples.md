# Java 中 StringWriter 追加(CharSequence)方法示例

> 原文:[https://www . geeksforgeeks . org/stringwriter-appendcharsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringwriter-appendcharsequence-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的 **append(CharSequence)** 方法用于在编写器上编写指定的 CharSequence。这个字符序列值被作为一个参数。

**语法:**

```
public StringWriter append(CharSequence charSequence)
```

**参数:**此方法接受一个强制参数**字符序列**，它是要写入编写器的字符序列。

**返回值:**这个方法返回这个 StringWriter 实例。

下面的程序说明了 append(CharSequence)方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// StringWriter append(CharSequence) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Write the CharSequence 'GeeksForGeeks'
            // to this writer using append() method
            // This will put the charSequence in the writer
            // till it is printed on the console
            writer.append("GeeksForGeeks");

            System.out.println(writer.toString());
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
// StringWriter append(CharSequence) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Write the CharSequence 'GFG'
            // to this writer using append() method
            // This will put the charSequence in the writer
            // till it is printed on the console
            writer.append("GFG");

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**