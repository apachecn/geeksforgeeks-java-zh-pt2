# Java 中的路径解析方法，示例

> 原文:[https://www . geesforgeks . org/path-resolvesibling-method-in-Java-with-examples/](https://www.geeksforgeeks.org/path-resolvesibling-method-in-java-with-examples/)

**resolveSibling()**[Java . nio . file . path](https://www.geeksforgeeks.org/tag/java-path/)**的**方法，用于根据该路径的父路径解析给定路径..

有两种类型的 resolveSibling()方法。

1.  **resolveSibling(Path other)** method of **[java.nio.file.Path](https://www.geeksforgeeks.org/tag/java-path/)** used to resolve the given path as parameter against this path’s parent path. This is very useful where a file name needs to be replaced with another file name. For example, suppose that the name separator is “/” and a path represents “drive/newFile/spring”, then invoking this method with the Path “plugin” will result in the Path “drive/newFile/plugin”. If this path does not have a parent path or other is absolute, then this method returns others. If other is an empty path then this method returns this path’s parent, or where this path doesn’t have a parent, the empty path.

    **语法:**

    ```
    default Path resolveSibling(Path other)

    ```

    **参数:**该方法接受单个参数**其他**，这是针对该路径的父路径进行解析的路径。

    **返回值:**此方法返回结果路径。

    下面的程序说明了解析(路径其他)方法:
    **程序 1:**

    ```
    // Java program to demonstrate
    // Path.resolveSibling(Path other) method

    import java.nio.file.Path;
    import java.nio.file.Paths;
    public class GFG {
        public static void main(String[] args)
        {

            // create object of Path
            Path path
                = Paths.get("drive\\temp\\Spring");

            // create an object of Path
            // to pass to resolve method
            Path path2
                = Paths.get("programes\\workspace");

            // call resolveSibling()
            // to create resolved Path
            // on parent of path object
            Path resolvedPath
                = path.resolveSibling(path2);

            // print result
            System.out.println("Resolved Path "
                               + "of path's parent:"
                               + resolvedPath);
        }
    }
    ```

    **Output:**![](img/a94460d749e93c120e194e3be09d01a3.png)
2.  **resolveSibling(String other)** method of **[java.nio.file.Path](https://www.geeksforgeeks.org/tag/java-path/)** used to converts a given path string which we passed as parameter to a Path and resolves it against this path’s parent path in exact same manner as specified by the resolveSibling method.

    **语法:**

    ```
    default Path resolveSibling(String other)

    ```

    **参数:**该方法接受单个参数**其他**，这是针对该路径的父路径解析的路径字符串。

    **返回值:**此方法返回结果路径。

    **异常:**如果路径字符串无法转换为路径，该方法抛出**invaliddathexception**。

    下面的程序说明了 resolveSibling(String other)方法:
    **程序 1:**

    ```
    // Java program to demonstrate
    // Path.resolveSibling(String other) method

    import java.nio.file.Path;
    import java.nio.file.Paths;
    public class GFG {
        public static void main(String[] args)
        {

            // create an object of Path
            Path path
                = Paths.get("drive\\temp\\Spring");

            // create a string object
            String passedPath = "drive";

            // call resolveSibling()
            // to create resolved Path
            // on parent of path object
            Path resolvedPath
                = path.resolveSibling(passedPath);

            // print result
            System.out.println("Resolved Path of "
                               + "path's parent:"
                               + resolvedPath);
        }
    }
    ```

    **Output:**![](img/07480bb13a69c1d873f425470b9b1023.png)

**参考文献:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # resolveSibling(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/nio/file/Path.html#resolveSibling(java.lang.String))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/path . html # resolveSibling(Java . nio . file . path)](https://docs.oracle.com/javase/10/docs/api/java/nio/file/Path.html#resolveSibling(java.nio.file.Path))