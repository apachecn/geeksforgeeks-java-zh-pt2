# Java 中的路径比较()方法，带示例

> 原文:[https://www . geesforgeks . org/path-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-compareto-method-in-java-with-examples/)

Java 7 中的 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了 Java **路径接口**。Path 接口位于 java.nio.file 包中，因此 Java Path 接口的完全限定名是 Java . nio . file . Path。Java Path 实例表示文件系统中的一个路径。路径可以用来定位文件或目录。实体的路径可以有两种类型:一种是绝对路径，另一种是相对路径。绝对路径是从根到实体的位置地址，而相对路径是相对于其他路径的位置地址。
**compare to(Java . nio . file . path)**方法 **java.nio.file.Path** 用于对两个抽象路径进行字典式的比较。这种方法可以比较两条路径。此方法定义的路径顺序是特定于提供者的，在默认提供者的情况下，是特定于平台的。如果参数等于此路径，则此方法返回零；如果此路径按字典顺序小于参数，则返回小于零的值；如果此路径按字典顺序大于参数，则返回大于零的值。此方法不访问文件系统。不需要文件就需要存在。此方法不能用于比较与不同文件系统提供程序关联的路径。
**语法:**

```
int compareTo(Path other)
```

**参数:**该方法接受单个参数另一条路径，即与当前路径相比的路径。
**返回值:**如果参数等于此路径，则此方法返回零，如果此路径在字典序上小于参数，则返回小于零的值，或者如果此路径在字典序上大于参数，则返回大于零的值。
**异常:**如果路径与不同的提供程序相关联，则该方法抛出异常**和**class castexception。
下面的程序说明了 compareTo(java.nio.file.Path)方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// Path.compareTo(Path) method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Paths
        Path path1
            = Paths.get("D:","eclipse","configuration","org.eclipse.update");

        Path path2
            = Paths.get("D:","eclipse","configuration","org.eclipse.update");

        // compare paths
        int value = path1.compareTo(path2);

        // print result
        if (value == 0)
            System.out.println("Both are equal");
        else if (value < 0)
            System.out.println("Path 2 is greater "
                               + "than path 1");
        else
            System.out.println("Path 1 is greater "
                               + "than path 2");
    }
}
```

**Output:** 

```
Both are equal
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// Path.compareTo(Path) method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Paths
        Path path1
            = Paths.get("D:","eclipse","configuration","org.eclipse.update");

        Path path2
            = Paths.get("D:\\temp\\Spring");

        // compare paths
        int value = path1.compareTo(path2);

        // print result
        if (value == 0)
            System.out.println("Both are equal");
        else if (value < 0)
            System.out.println("Path 2 is greater "
                               + "than path 1");
        else
            System.out.println("Path 1 is greater "
                               + "than path 2");
    }
}
```

**Output**

```
Path 2 is greater than path 1

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # compare to(Java . nio . file . path)](https://docs.oracle.com/javase/10/docs/api/java/nio/file/Path.html#compareTo(java.nio.file.Path))