# 用示例将 toString()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-tostring-method-in-java-with-examples/)

**[java.lang.Package 类](https://www.geeksforgeeks.org/java-lang-package-java/)** 的 **toString()** 方法用于获取这个包实例的字符串表示。方法将字符串表示形式作为字符串值返回。

**语法:**

```
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法将**字符串**表示作为字符串值返回。

下面的程序演示了 toString()方法。

**例 1:**

```
// Java program to demonstrate
// toString() method

public class Test {
    public static void main(String[] args)
    {

        // returns the Package
        // object for this package
        Package myPackage
            = Package.getPackage("java.lang");

        // get the String representation of this package
        // using toString() method
        System.out.println(
            "String representation: "
            + myPackage.toString());
    }
}
```

**输出:**

```
String representation: package java.lang, Java Platform API Specification, version 1.8

```

**例 2:**

```
// Java program to demonstrate
// toString() method

public class Test {
    public static void main(String[] args)
    {

        // returns the Package
        // object for this package
        Package myPackage
            = Package.getPackage("java.io");

        // get the toString value of this package
        // using toString() method
        System.out.println(
            "String representation: "
            + myPackage.toString());
    }
}
```

**输出:**

```
String representation: package java.io, Java Platform API Specification, version 1.8

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#toString--)