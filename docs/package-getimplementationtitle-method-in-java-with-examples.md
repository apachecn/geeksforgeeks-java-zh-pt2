# 用示例将 getImplementationTitle()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-getimplementation title-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getimplementationtitle-method-in-java-with-examples/)

**[java.lang.Package 类](https://www.geeksforgeeks.org/java-lang-package-java/)** 的 **getImplementationTitle()** 方法用于获取此包的实现标题。方法以字符串形式返回包的实现标题。

**语法:**

```
public String getImplementationTitle()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法将包的**实现标题**作为字符串返回，如果知道的话。否则返回空值

下面的程序演示了 getImplementationTitle()方法。

**例 1:**

```
// Java program to demonstrate
// getImplementationTitle() method

public class Test {
    public static void main(String[] args)
    {

        // returns the Package
        // object for this package
        Package myPackage
            = Package.getPackage("java.lang");

        System.out.println(
            "Package represented by myPackage: "
            + myPackage.toString());

        // Get the implementation title of myPackage
        // using getImplementationTitle() method
        System.out.println(
            "Implementation title of myPackage: "
            + myPackage.getImplementationTitle());
    }
}
```

**输出:**

```
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Implementation title of myPackage: Java Runtime Environment

```

**例 2:**

```
// Java program to demonstrate
// getImplementationTitle() method

public class Test {
    public static void main(String[] args)
    {

        // returns the Package
        // object for this package
        Package myPackage
            = Package.getPackage("java.io");

        System.out.println(
            "Package represented by myPackage: "
            + myPackage.toString());

        // Get the name of myPackage
        // using getImplementationTitle() method
        System.out.println(
            "Implementation title of myPackage: "
            + myPackage.getImplementationTitle());
    }
}
```

**输出:**

```
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Implementation title of myPackage: Java Runtime Environment

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getImplementationTitle–](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#getImplementationTitle--)