# Java 中路径 getName(int)方法，示例

> 原文:[https://www . geesforgeks . org/path-getnameint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-getnameint-method-in-java-with-examples/)

Java 7 中的 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了 Java **路径接口**。Path 接口位于 java.nio.file 包中，因此 Java Path 接口的完全限定名是 Java . nio . file . Path。Java Path 实例表示文件系统中的一个路径。路径可以用来定位文件或目录。实体的路径可以有两种类型:一种是绝对路径，另一种是相对路径。绝对路径是从根到实体的位置地址，而相对路径是相对于其他路径的位置地址。
****Java . nio . file . Path**的 getName(int index)** 方法，用于返回该路径的一个 Name 元素作为 Path 对象。我们将索引作为参数传递，索引表示要返回的 name 元素的索引。目录层次结构中最接近根的元素的索引为 0。离根最远的元素的索引计数为-1。
**语法:**

```java
Path getName(int index)
```

**参数:**该方法接受单个参数索引，即元素的索引。
**返回值:**这个方法返回名称元素。
**异常:**此方法抛出和异常 **IllegalArgumentException** 如果索引为负，则索引大于或等于元素数，或者此路径没有名称元素。
以下程序说明 getName(int index)方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// java.nio.file.Path.getName(int index) method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path
            = Paths.get("D:\\temp\\DS and algo"
                        + "\\algorithm and data struc"
                        + "\\Problem sets");

        // call getName(int i) to get the
        // element at index i
        Path indexpath = path.getName(3);

        // print ParentPath
        System.out.println("Index 3: "
                           + indexpath);
    }
}
```

**Output:** 

```java
Index 3: Problem sets
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// java.nio.file.Path.getName(int index) method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path
            = Paths.get("D:\\eclipse\\configuration"
                        + "\\org.eclipse.update");

        // call getName(int i) to get
        // the element at index i
        Path indexpath = path.getName(2);

        // print ParentPath
        System.out.println("Index 2: "
                           + indexpath);
    }
}
```

**Output:** 

```java
Index 2: org.eclipse.update
```

**参考文献:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # getName(int)T4】