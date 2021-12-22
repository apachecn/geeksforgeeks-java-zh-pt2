# Java 中的 Path getParent()方法，示例

> 原文:[https://www . geesforgeks . org/path-getparent-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-getparent-method-in-java-with-examples/)

Java 7 中的 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了 Java **路径接口**。Path 接口位于 java.nio.file 包中，因此 Java Path 接口的完全限定名是 Java . nio . file . Path。Java Path 实例表示文件系统中的一个路径。路径可以用来定位文件或目录。实体的路径可以有两种类型:一种是绝对路径，另一种是相对路径。绝对路径是从根到实体的位置地址，而相对路径是相对于其他路径的位置地址。

**getParent()** 方法的 **java.nio.file.Path** 用来返回当前路径对象的父路径，如果该路径没有父路径则为 null。此路径对象的父路径由此路径的根组件和路径中的每个元素组成，但离目录层次结构中的根最远的元素除外。如果此路径有多个元素，并且没有根组件，则此方法相当于计算表达式:

```java
subpath(0, getNameCount()-1);
```

**语法:**

```java
Path getParent()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个表示路径父路径的路径。

以下程序说明 getParent()方法:
**程序 1:**

```java
// Java program to demonstrate
// java.nio.file.Path.getParent() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path
            = Paths.get("D:/workspace/AmanCV.docx");

        // call getParent() to get parent path
        Path parentPath = path.getParent();

        // print ParentPath
        System.out.println("Parent Path: "
                           + parentPath);
    }
}
```

**Output:**

```java
Parent Path: D:/workspace

```

**程序 2:**

```java
// Java program to demonstrate
// java.nio.file.Path.getParent() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path = Paths.get("D:/Resume.pdf");

        // call getParent() to get parent path
        Path parentPath = path.getParent();

        // print ParentPath
        System.out.println("Parent Path: "
                           + parentPath);
    }
}
```

**Output:**

```java
Parent Path: D:

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # getParent()](https://docs.oracle.com/javase/10/docs/api/java/nio/file/Path.html#getParent())