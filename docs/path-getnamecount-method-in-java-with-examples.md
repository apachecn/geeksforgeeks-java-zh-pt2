# Java 中的 Path getNameCount()方法，带示例

> 原文:[https://www . geesforgeks . org/path-getname count-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-getnamecount-method-in-java-with-examples/)

**Java 7** 中 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了**路径界面**。Path 接口位于 java.nio.file 包中，因此 Java Path 接口的完全限定名是 Java . nio . file . Path。Java Path 实例表示文件系统中的一个路径。路径可以用来定位文件或目录。实体的路径可以有两种类型:一种是绝对路径，另一种是相对路径。绝对路径是从根到实体的位置地址，而相对路径是相对于其他路径的位置地址。

**getNameCount()** 方法的 **java.nio.file.Path** 用来返回路径中名称元素的个数。如果这个路径只代表一个根组件，那么方法将返回 1。

**语法:**

```java
int getNameCount()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回路径中的元素个数，如果该路径只代表一个根组件，则返回 1。

下面的程序说明了 getNameCount()方法:
**程序 1:**

```java
// Java program to demonstrate
// java.nio.file.Path.getNameCount() method

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

        // call getNameCount()
        int nameCount = path.getNameCount();

        // print NameCount
        System.out.println("NameCount in Path: "
                           + nameCount);
    }
}
```

**Output:**

```java
NameCount in Path: 3

```

**程序 2:**

```java
// Java program to demonstrate
// java.nio.file.Path.getNameCount() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path = Paths.get("D:/Resume.pdf");

        // call getNameCount()
        int nameCount = path.getNameCount();

        // print NameCount
        System.out.println("NameCount in Path: "
                           + nameCount);
    }
}
```

**Output:**

```java
NameCount in Path: 2

```

**程序 3:**

```java
// Java program to demonstrate
// java.nio.file.Path.getNameCount() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path = Paths.get("D:");

        // call getNameCount()
        int nameCount = path.getNameCount();

        // print NameCount
        System.out.println("NameCount in Path: "
                           + nameCount);
    }
}
```

**Output:**

```java
NameCount in Path: 1

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # getNameCount()](https://docs.oracle.com/javase/10/docs/api/java/nio/file/Path.html#getNameCount())