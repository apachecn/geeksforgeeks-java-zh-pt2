# Java 中的 Path toString()方法，带示例

> 原文:[https://www . geesforgeks . org/path-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-tostring-method-in-java-with-examples/)

Java 7 中的 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了 Java **路径接口**。 **toString()** 方法的 **java.nio.file.Path** 用来返回这个路径的字符串表示。如果此路径是通过使用 getPath 方法转换路径字符串而创建的，则此方法返回的路径字符串可能不同于用于创建路径的原始字符串。此方法返回的路径使用默认的名称分隔符来分隔路径中的名称。

**语法:**

```
String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个路径的字符串表示。

下面的程序说明了 toString()方法:
**程序 1:**

```
// Java program to demonstrate
// java.nio.file.Path.toAbsolute() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path
            = Paths.get("C:\\Program Files\\"
                        + "Java\\jre1.8.0_211");

        // print path
        System.out.println("Path: "
                           + path.toString());
    }
}
```

**Output:**

```
Path: C:\Program Files\Java\jre1.8.0_211

```

**程序 2:**

```
// Java program to demonstrate
// java.nio.file.Path.toString() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path
            = Paths.get("C:\\Users\\"
                        + "asingh.one\\Documents");

        // print path
        System.out.println("Path: "
                           + path.toString());
    }
}
```

**Output:**

```
Path: C:\Users\asingh.one\Documents

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/nio/file/Path.html#toString())