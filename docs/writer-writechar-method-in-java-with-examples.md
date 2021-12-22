# Writer 用 Java 写(char[])方法，示例

> 原文:[https://www . geesforgeks . org/writer-write char-method-in-Java-with-examples/](https://www.geeksforgeeks.org/writer-writechar-method-in-java-with-examples/)

Java 中 **[Writer](https://www.geeksforgeeks.org/java-io-Writer-class-java-set-1/)** 类的 **write(char[])** 方法用于在流上写入指定的字符数组。这个字符数组作为一个参数。

**语法:**

```
public void write(char[] charArray)
```

**参数:**该方法接受一个强制参数**字符数组**，它是要写入流中的字符数组。

**返回值:**此方法不返回值。

下面的方法说明了 write(char[])方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// Writer write(char[]) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Get the character array
            // to be written in the stream
            char[] charArray = { 'G', 'e', 'e', 'k', 's',
                                 'F', 'o', 'r',
                                 'G', 'e', 'e', 'k', 's' };

            // Write the charArray
            // to this writer using write() method
            // This will put the charArray in the stream
            // till it is printed on the console
            writer.write(charArray);

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
// Writer write(char[]) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a Writer instance
            Writer writer
                = new PrintWriter(System.out);

            // Get the character array
            // to be written in the stream
            char[] charArray = { 'G', 'F', 'G' };

            // Write the charArray
            // to this writer using write() method
            // This will put the charArray in the stream
            // till it is printed on the console
            writer.write(charArray);

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