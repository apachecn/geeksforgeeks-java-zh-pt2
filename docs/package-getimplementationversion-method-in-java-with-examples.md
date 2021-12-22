# 用示例将 getImplementationVersion()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-getimplementationversion-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getimplementationversion-method-in-java-with-examples/)

**[java.lang.Package 类](https://www.geeksforgeeks.org/java-lang-package-java/)** 的**getImplementationVersion()**方法用于获取该包的实现版本。方法以字符串形式返回包的实现版本。

**语法:**

```
public String getImplementationVersion()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法将包的**实现版本**作为字符串返回，如果已知的话。否则返回空值

下面的程序演示了 getImplementationVersion()方法。

**例 1:**

```
// Java program to demonstrate
// getImplementationVersion() method

public class Test {
    public static void main(String[] args)
    {

        // returns the Package object
        // for this package
        Package myPackage
            = Package.getPackage("java.lang");

        System.out.println(
            "Package represented by myPackage: "
            + myPackage.toString());

        // Get the implementation version of myPackage
        // using getImplementationVersion() method
        System.out.println(
            "Implementation version of myPackage: "
            + myPackage.getImplementationVersion());
    }
}
```

**输出:**

```
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Implementation version of myPackage: 1.8.0_181

```

**例 2:**

```
// Java program to demonstrate
// getImplementationVersion() method

public class Test {
    public static void main(String[] args)
    {

        // returns the Package object
        // for this package
        Package myPackage
            = Package.getPackage("java.io");

        System.out.println(
            "Package represented by myPackage: "
            + myPackage.toString());

        // Get the name of myPackage
        // using getImplementationVersion() method
        System.out.println(
            "Implementation version of myPackage: "
            + myPackage.getImplementationVersion());
    }
}
```

**输出:**

```
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Implementation version of myPackage: 1.8.0_181

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getImplementationVersion–](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#getImplementationVersion--)