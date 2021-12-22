# 用示例将 getSpecificationTitle()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-getspecificationtitle-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getspecificationtitle-method-in-java-with-examples/)

[**java.lang.Package 类**](https://www.geeksforgeeks.org/java-lang-package-java/) 的 **getSpecificationTitle()** 方法用于获取该包的规格标题。方法以字符串形式返回包的规范标题。
**语法:**

```
public String getSpecificationTitle()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法将包的**规格标题**作为字符串返回，如果知道的话。否则返回空值
下面的程序演示了 getSpecificationTitle()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getSpecificationTitle() method

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

        // Get the specification title of myPackage
        // using getSpecificationTitle() method
        System.out.println(
            "Specification title of myPackage: "
            + myPackage.getSpecificationTitle());
    }
}
```

**Output:** 

```
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Specification title of myPackage: Java Platform API Specification
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getSpecificationTitle() method

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
        // using getSpecificationTitle() method
        System.out.println(
            "Specification title of myPackage: "
            + myPackage.getSpecificationTitle());
    }
}
```

**Output:** 

```
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Specification title of myPackage: Java Platform API Specification
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getspecification title–](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#getSpecificationTitle--)