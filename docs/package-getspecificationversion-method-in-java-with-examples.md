# 用 Java 打包 getSpecificationVersion()方法，示例

> 原文:[https://www . geesforgeks . org/package-getspecificationversion-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getspecificationversion-method-in-java-with-examples/)

**[java.lang.Package 类](https://www.geeksforgeeks.org/java-lang-package-java/)** 的**getspecification version()**方法用于获取该包的规范版本。方法以字符串形式返回包的规范版本。

**语法:**

```
public String getSpecificationVersion()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法将包的**规格版本**作为字符串返回，如果已知的话。否则返回空值

下面的程序演示了 getSpecificationVersion()方法。

**例 1:**

```
// Java program to demonstrate
// getSpecificationVersion() method

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

        // Get the specification version of myPackage
        // using getSpecificationVersion() method
        System.out.println(
            "Specification version of myPackage: "
            + myPackage.getSpecificationVersion());
    }
}
```

**输出:**

```
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Specification version of myPackage: 1.8

```

**例 2:**

```
// Java program to demonstrate
// getSpecificationVersion() method

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
        // using getSpecificationVersion() method
        System.out.println(
            "Specification version of myPackage: "
            + myPackage.getSpecificationVersion());
    }
}
```

**输出:**

```
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Specification version of myPackage: 1.8

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getspecification version–](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#getSpecificationVersion--)