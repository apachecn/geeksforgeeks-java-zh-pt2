# Java 中的 streamForceDexception

> 原文:[https://www . geeksforgeeks . org/streamforgetexception-in-Java/](https://www.geeksforgeeks.org/streamcorruptedexception-in-java/)

[对象流异常](https://docs.oracle.com/javase/7/docs/api/java/io/ObjectStreamException.html)的类**流损坏异常**是从对象流中读取的控制信息违反内部一致性检查时引发的异常。它将创建一个 StreamCorruptedException，并列出引发异常的原因。如果构造函数中没有传递任何参数，那么它将创建一个 StreamCorruptedException，并且不列出引发异常的原因。

**语法:**

```java
public StreamCorruptedException(String reason)
```

**参数:**原因–“字符串”描述异常原因

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate StreamCorruptedException

// Importing required classes
import java.io.*;
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.StreamCorruptedException;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Creating an object of InputStream class
        InputStream in = new FileInputStream("testout.txt");

        // Representing input object in form of string
        DataInputStream dis = new DataInputStream(in);

        // Writing the data

        // Try block to check if exception occurs
        try {

            // readByte will read single byte from the file
            if (dis.readByte() != 1) {
                throw new StreamCorruptedException(
                    "File format not recognised");

                // If file contains NULL in first byte
                // then exception will be thrown
            }
        }

        // Catch block 1
        // Handling stream corrupted exception
        catch (StreamCorruptedException e) {

            // Display message on console if
            // StreamCorruptException occurs
            System.out.println(e);
        }

        // Catch block 2
        // Handling basic I/O exception
        catch (Exception e) {

            // If EOF exception or any other exception
            // occurs
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.io.StreamCorruptedException: File format not recognised
```

现在讨论第二个例子，其中文件格式被识别。在实施之前，请仔细阅读下面的示例注释，如下所示。

> **注意:**将 C098.txt 文件制作在程序的同一个文件夹中，照原样复制下面的片段。这是一个示例损坏文件

> C098.txt
> 
> ```java
> ¬í sr Product        L desct Ljava / lang / String;
> 
> L priceq ~ L
> 
>        productIdq ~ xpt Bookt Rs .200t P001¬í sr
> 
> Product        L desct Ljava / lang / String; L
> 
> priceq ~ L productIdq ~ xpt Laptopt Rs .45, 500t P087
> ```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate StreamCorruptedException

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
// To illustrate object stream exception
class GFG {

    // Main driver method
    public static void main(String args[]) throws Exception
    {

        // Text in file is stored as a string
        String CId = "C098.txt";
        File objFile1 = new File(CId);

        // Try block to check fo exception
        try {

            // Creating an object of FileInputStream class
            FileInputStream objFIS
                = new FileInputStream(objFile1);

            // Creating an object of ObjectInputStream class
            ObjectInputStream objI
                = new ObjectInputStream(objFIS);

            Object obj = null;
        }

        // Catch block 1
        // Handling stream corrupted exception
        catch (StreamCorruptedException ex) {

            // Display this message as exception is caught
            System.out.println(
                "Stream Corrupted Exception Occured");
        }
        // Catch block 2
        // Handling basic I/O exceptions
        catch (Exception e) {

            // Print statement
            System.out.println("Hello");
        }
    }
}
```

**输出:**

```java
Stream Corrupted Exception Occured
```