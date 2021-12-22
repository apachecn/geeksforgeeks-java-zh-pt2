# Java 中的 ZipFile getComment()函数，带示例

> 原文:[https://www . geesforgeks . org/zipfile-getcomment-function-in-Java-with-examples/](https://www.geeksforgeeks.org/zipfile-getcomment-function-in-java-with-examples/)

**getComment()** 函数是 java.util.zip 包的一部分。该函数返回一个字符串，该字符串是 zip 文件的注释。

**功能签名:**

```
public String getComment()
```

**语法:**

```
zip_file.getComment();
```

**参数:**函数不需要任何参数
**返回值:**函数返回一个 String，是 zip 文件的注释

**异常:**如果压缩文件已经关闭，函数抛出**非法状态异常**

**以下程序说明了 getComment()功能的使用**

**示例 1:** 创建一个名为 zip_file 的文件，并使用 getComment()函数获取注释。“file.zip”是 f:目录中的一个 zip 文件。

```
// Java program to demonstrate the
// use of getComment() function

import java.util.zip.*;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file.zip");

            // Display the comment
            // of the zip file
            // using getComment() function
            System.out.println("comment = "
                               + zip_file.getComment());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```
comment = This is a zip file comment

```

**示例 2:** 创建一个名为 zip_file 的文件，并使用 getComment()函数获取注释。如果我们关闭文件，然后调用函数 getComment()，这个函数将引发异常。

```
// Java program to demonstrate the
// use of getComment() function

import java.util.zip.*;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file.zip");

            // close the file
            zip_file.close();

            // Display the comment
            // of the zip file
            // using getComment() function
            System.out.println("comment = "
                               + zip_file.getComment());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```
zip file closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/zipfile . html # getComment()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/ZipFile.html#getComment())