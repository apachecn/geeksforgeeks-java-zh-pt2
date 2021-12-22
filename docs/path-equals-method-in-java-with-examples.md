# Java 中的 Path equals()方法，示例

> 原文:[https://www . geesforgeks . org/path-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-equals-method-in-java-with-examples/)

Java 7 中的 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了 Java **路径接口**。Path 接口位于 java.nio.file 包中，因此 Java Path 接口的完全限定名是 Java . nio . file . Path。Java Path 实例表示文件系统中的一个路径。路径可以用来定位文件或目录。实体的路径可以有两种类型:一种是绝对路径，另一种是相对路径。绝对路径是从根到实体的位置地址，而相对路径是相对于其他路径的位置地址。

**equals()** 方法的 **java.nio.file.Path** 用于比较该路径是否与作为参数传递的对象相等。如果给定的对象不是路径或者是与不同文件系统相关联的路径，则该方法返回 false。当且仅当给定对象是与此路径相同的路径时，此方法返回 true。

**语法:**

```
boolean equals(Object other)

```

**参数:**该方法接受一个参数作为要比较的另一个对象。

**返回值:**当且仅当给定对象是与该路径相同的路径时，该方法返回真。

下面的程序说明了 equals()方法:
**程序 1:**

```
// Java program to demonstrate
// java.nio.file.Path.equals() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Paths
        Path path1
            = Paths.get("D:\\eclipse\\configuration"
                        + "\\org.eclipse.update");

        Path path2
            = Paths.get("D:\\eclipse\\configuration"
                        + "\\org.eclipse.update");

        // compare paths for equality
        boolean response
            = path1.equals(path2);

        // print result
        if (response)
            System.out.println("Both are equal");
        else
            System.out.println("Both are not equal");
    }
}
```

**Output:**

```
Both are equal

```

**程序 2:**

```
// Java program to demonstrate
// java.nio.file.Path.equals() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Paths
        Path path1
            = Paths.get("D:\\eclipse\\configuration"
                        + "\\org.eclipse.update");

        Path path2
            = Paths.get("D:\\temp\\Spring");

        // compare paths for equality
        boolean response = path1.equals(path2);

        // print result
        if (response)
            System.out.println("Both are equal");
        else
            System.out.println("Both are not equal");
    }
}
```

**Output:**

```
Both are not equal

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # equals()](https://docs.oracle.com/javase/10/docs/api/java/nio/file/Path.html#equals())