# Java 中的 ZipFile getName()函数，带示例

> 原文:[https://www . geesforgeks . org/zipfile-getname-function-in-Java-with-examples/](https://www.geeksforgeeks.org/zipfile-getname-function-in-java-with-examples/)

**getName()** 函数是 java.util.zip 包的一部分。该函数返回 ZipFile 对象的路径名。

**功能签名:**

```
public String getName()
```

**语法:**

```
zip_file.getName();
```

**参数:**函数不需要任何参数
**返回值:**函数返回一个字符串，是 zip 文件
**的路径名异常:**函数不抛出任何异常。

**以下程序说明了 getName()功能的使用**

**示例 1:** 创建一个名为 zip_file 的文件，并使用 getName()函数获取名称。“file.zip”是 f:目录中的一个 zip 文件。

```
// Java program to demonstrate the
// use of getName() function

import java.util.zip.*;

public class solution {
    public static void main(String args[])
    {
        try {
            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file.zip");

            // Display the name of the zip file
            // using getName() function
            System.out.println(zip_file.getName());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```
f:\file.zip

```

**示例 2:** 创建一个名为 zip_file 的文件，并使用 getName()函数获取名称。“file1.zip”是 f:目录中不存在的 zip 文件。

```
// Java program to demonstrate the
// use of getName() function

import java.util.zip.*;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create a Zip File
            ZipFile zip_file
                = new ZipFile("f:\\file1.zip");

            // Display the name of the zip file
            // using getName() function
            System.out.println(zip_file.getName());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```
f:\file1.zip (The system cannot find the file specified)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/zipfile . html # getName()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/ZipFile.html#getName())