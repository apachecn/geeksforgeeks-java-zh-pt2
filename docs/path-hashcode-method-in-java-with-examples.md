# Java 中的 Path hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/path-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-hashcode-method-in-java-with-examples/)

Java 7 中的 [Java NIO](https://www.geeksforgeeks.org/tag/java-nio-package/) 增加了 Java **路径接口**。 **hashCode()** 方法的 **java.nio.file.Path** 用于在计算 hashCode 后返回该路径的哈希代码。如果对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希相关算法进行一些操作，比如哈希表、哈希表等。也可以用对象的唯一代码(hashcode)来搜索对象。

**语法:**

```java
int hashCode()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该路径的哈希码值。

下面的程序说明了 hashCode()方法:
**程序 1:**

```java
// Java program to demonstrate
// java.nio.file.Path.hashCode() method

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

        // call hashCode() to get hashCode
        int hashCode = path.hashCode();

        // print hashCode
        System.out.println("Hash Code: "
                           + hashCode);
    }
}
```

**Output:**

```java
Hash Code: 1600751599

```

**程序 2:**

```java
// Java program to demonstrate
// java.nio.file.Path.hashCode() method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // create object of Path
        Path path = Paths.get("D:/Resume.pdf");

        // call hashCode() to get hashCode
        int hashCode = path.hashCode();

        // print hashCode
        System.out.println("Hash Code: "
                           + hashCode);
    }
}
```

**Output:**

```java
Hash Code: -996777206

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/nio/file/Path.html#hashCode())