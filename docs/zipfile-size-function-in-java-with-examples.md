# Java 中的 ZipFile size()函数，带示例

> 原文:[https://www . geesforgeks . org/zipfile-size-function-in-Java-with-examples/](https://www.geeksforgeeks.org/zipfile-size-function-in-java-with-examples/)

**size()** 函数是 java.util.zip 包的一部分。该函数返回 zip 文件的条目数。

**功能签名:**

```
public int size()
```

**语法:**

```
zip_file.size();
```

**参数:**该函数不需要任何参数
**返回值:**该函数返回一个整数，该整数是 zip 文件
**的条目数异常:**如果 zip 文件已经关闭，该函数抛出**illegalsteexception**

**下面的程序说明了使用 size()函数**
**示例 1:** 创建一个名为 zip_file 的文件，并使用 size()函数获取条目数。“file.zip”是 f:目录中的一个 zip 文件。

```
// Java program to demonstrate the
// use of size() function

import java.util.zip.*;

public class solution {
    public static void main(String args[])
    {
        try {

            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file.zip");

            // Display the number of entries
            // of the zip file
            // using size() function
            System.out.println("number of entries = "
                               + zip_file.size());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```
number of entries= 7

```

**示例 2:** 创建一个名为 zip_file 的文件，使用 size()函数获取条目数。如果我们关闭文件，然后调用函数 size()，我们将尝试查看函数是否抛出异常。

```
// Java program to demonstrate the
// use of size() function

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

            // Display the number of entries
            // of the zip file
            // using size() function
            System.out.println("number of entries = "
                               + zip_file.size());
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

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/zipfile . html # size()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/ZipFile.html#size())