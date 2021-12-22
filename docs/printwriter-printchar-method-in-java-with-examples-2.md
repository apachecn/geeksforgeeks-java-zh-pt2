# PrintWriter 用 Java 打印(char[])方法，示例

> 原文:[https://www . geesforgeks . org/print writer-print char-method-in-Java-with-examples-2/](https://www.geeksforgeeks.org/printwriter-printchar-method-in-java-with-examples-2/)

Java 中 **[PrintWriter](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)** 类的 **print(char[])** 方法用于打印流上指定的字符数组。这个字符数组作为一个参数。

**语法:**

```
public void print(char[] charArray)
```

**参数:**该方法接受一个强制参数**字符数组**，它是要在流中打印的字符数组。

**返回值:**此方法不返回值。

**异常:**如果指定的 charArray()为空，此方法返回**空指针异常**。

下面的方法说明了 print(char[])方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// PrintWriter print(char[]) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the character array
            // to be printed in the stream
            char[] charArray = { 'G', 'e', 'e', 'k', 's',
                                 'F', 'o', 'r',
                                 'G', 'e', 'e', 'k', 's' };

            // print the charArray
            // to this writer using print() method
            // This will put the charArray in the stream
            // till it is printed on the console
            writer.print(charArray);

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
// PrintWriter print(char[]) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the character array
            // to be printed in the stream
            char[] charArray = { 'G', 'F', 'G' };

            // print the charArray
            // to this writer using print() method
            // This will put the charArray in the stream
            // till it is printed on the console
            writer.print(charArray);

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