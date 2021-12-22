# Java 中的 ZipFile entries()函数，带示例

> 原文:[https://www . geesforgeks . org/zipfile-entries-function-in-Java-with-examples/](https://www.geeksforgeeks.org/zipfile-entries-function-in-java-with-examples/)

**entries()** 函数是 java.util.zip 包的一部分。该函数返回 zip 文件的 zip 文件条目的枚举。

**功能签名:**

```java
public Enumeration entries()
```

**语法:**

```java
zip_file.entries();
```

**参数:**该功能不需要任何参数

**返回值:**函数返回 zip 文件的 zip 文件条目的枚举，该枚举包含 zip 文件中所有文件的 ZipEntry。

**异常:**如果压缩文件已经关闭，函数抛出**非法状态异常**。

**以下程序说明了条目()功能的使用**

**示例 1:** 创建一个名为 zip_file 的文件，并使用 entries()函数获取 zip 文件条目。“file.zip”是 f:目录中的一个 zip 文件。

```java
// Java program to demonstrate the
// use of entries() function

import java.util.zip.*;
import java.util.Enumeration;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file.zip");

            // get the Zip Entries using
            // the entries() function
            Enumeration<? extends ZipEntry> entries
                = zip_file.entries();

            System.out.println("Entries:");

            // iterate through all the entries
            while (entries.hasMoreElements()) {
                // get the zip entry
                ZipEntry entry = entries.nextElement();

                // display the entry
                System.out.println(entry.getName());
            }
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
Entries:
file3.cpp
file1.cpp
file2.cpp

```

**示例 2:** 创建一个名为 zip_file 的文件，并使用 entries()函数获取 zip 文件条目。如果我们关闭文件，然后调用函数条目()，此函数将引发异常。

```java
// Java program to demonstrate the
// use of entries() function

import java.util.zip.*;
import java.util.Enumeration;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file.zip");

            // close the zip file
            zip_file.close();

            // get the Zip Entries using
            // the entries() function
            Enumeration<? extends ZipEntry> entries
                = zip_file.entries();

            System.out.println("Entries:");

            // iterate through all the entries
            while (entries.hasMoreElements()) {

                // get the zip entry
                ZipEntry entry = entries.nextElement();

                // display the entry
                System.out.println(entry.getName());
            }
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
zip file closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/zipfile . html # entries()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/ZipFile.html#entries())