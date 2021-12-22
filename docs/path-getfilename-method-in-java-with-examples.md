# Java 中的路径 getFileName()方法，示例

> 原文:[https://www . geesforgeks . org/path-get filename-in-Java-method-with-examples/](https://www.geeksforgeeks.org/path-getfilename-method-in-java-with-examples/)

**Java 7** 中 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了**路径界面**。Path 接口位于 java.nio.file 包中，因此 Java Path 接口的完全限定名是 Java . nio . file . Path。Java Path 实例表示文件系统中的一个路径。路径可以用来定位文件或目录。实体的路径可以有两种类型:一种是绝对路径，另一种是相对路径。绝对路径是从根到实体的位置地址，而相对路径是相对于其他路径的位置地址。

**getFileName()** 方法的 **java.nio.file.Path** 用来返回这个 Path 对象指向的文件或目录的名称。文件名是目录层次结构中离根最远的元素。

**语法:**

```
Path getFileName()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该路径对象指向的文件或目录的名称。

下面的程序说明了 getFileName()方法:
**程序 1:**

```
// Java program to demonstrate
// java.nio.file.Path.getFileName() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path = Paths.get("D:/workspace/AmanCV.docx");

        // call getFileName() and get FileName path object
        Path fileName = path.getFileName();

        // print FileName
        System.out.println("FileName: "
                           + fileName.toString());
    }
}
```

**Output:**

```
FileName: AmanCV.docx

```

**程序 2:**

```
// Java program to demonstrate
// java.nio.file.Path.getFileName() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path = Paths.get("D:/Resume.pdf");

        // call getFileName() and get FileName path object
        Path fileName = path.getFileName();

        // print FileName
        System.out.println("FileName: "
                           + fileName.toString());
    }
}
```

**Output:**

```
FileName: Resume.pdf

```

**参考文献:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # getFileName()