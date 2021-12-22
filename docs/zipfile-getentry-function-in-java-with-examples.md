# Java 中的 ZipFile getEntry()函数，带示例

> 原文:[https://www . geesforgeks . org/zipfile-getentry-function-in-Java-with-examples/](https://www.geeksforgeeks.org/zipfile-getentry-function-in-java-with-examples/)

**getEntry()** 函数是 java.util.zip 包的一部分。该函数返回由字符串参数指定的 zip 文件中存在的文件的 ZipEntry。

**功能签名:**

```
public ZipEntry getEntry(String name)
```

**语法:**

```
zip_file.getEntry();
```

**参数:**函数取一个字符串参数，即文件名。
**返回值:**该函数返回字符串参数指定的 zip 文件的 ZipEntry。
**异常:**如果 zip 文件已经关闭，函数抛出**illegalstatexception**。

**以下程序说明了 getEntry()功能的使用**

**示例 1:** 创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目。“file.zip”是 f:目录中的一个 zip 文件。

```
// Java program to demonstrate the
// use of getEntry() function

import java.util.zip.*;
import java.util.Enumeration;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file.zip");

            // get the Zip Entry using
            // the getEntry() function
            ZipEntry entry
                = zip_file.getEntry("file1.cpp");

            // display the Zip Entry
            System.out.println("Name: "
                               + entry.getName());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```
Name: file1.cpp

```

**示例 2:** 创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目。“file.zip”是存在于 f:目录中的 zip 文件，而“file4.cpp”不存在于 zip 文件中。

```
// Java program to demonstrate the
// use of getEntry() function

import java.util.zip.*;
import java.util.Enumeration;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file.zip");

            // get the Zip Entry using
            // the getEntry() function
            ZipEntry entry
                = zip_file.getEntry("file4.cpp");

            // display the Zip Entry
            System.out.println("Name: "
                               + entry.getName());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```
null

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/zipfile . html # getEntry(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/util/zip/ZipFile.html#getEntry(java.lang.String))