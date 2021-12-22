# Java 中的路径 getFileSystem()方法，示例

> 原文:[https://www . geesforgeks . org/path-getfile system-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-getfilesystem-method-in-java-with-examples/)

**Java 7** 中 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了**路径界面**。Path 接口位于 java.nio.file 包中，因此 Java Path 接口的完全限定名是 Java . nio . file . Path。Java Path 实例表示文件系统中的一个路径。路径可以用来定位文件或目录。实体的路径可以有两种类型:一种是绝对路径，另一种是相对路径。绝对路径是从根到实体的位置地址，而相对路径是相对于其他路径的位置地址。

**getFileSystem()** 方法的 **java.nio.file.Path** 用来返回创建这个 Path 对象的文件系统。

**语法:**

```java
FileSystem getFileSystem()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回创建此 Path 对象的文件系统。

下面的程序说明了 getFileSystem()方法:
**程序 1:**

```java
// Java program to demonstrate
// java.nio.file.Path.getFileSystem() method

import java.io.IOException;
import java.nio.file.FileSystem;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path
            = Paths.get("D:/workspace/AmanCV.docx");

        // call getFileSystem()
        // and get FileSystem object
        FileSystem fs = path.getFileSystem();

        // print separator of FileSystem
        System.out.println("Separator used for FileSystem: "
                           + fs.getSeparator());
    }
}
```

**Output:**

```java
Separator used for FileSystem: /

```

**程序 2:**

```java
// Java program to demonstrate
// java.nio.file.Path.getFileSystem() method

import java.io.IOException;
import java.nio.file.FileSystem;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path = Paths.get("D:/Resume.pdf");

        // call getFileSystem()
        // and get FileSystem object
        FileSystem fs = path.getFileSystem();

        // print FileSystem is ReadOnly or not
        System.out.println("FileSystem is ReadOnly: "
                           + fs.isReadOnly());
    }
}
```

**Output:**

```java
FileSystem is ReadOnly: false

```

**参考文献:**T2