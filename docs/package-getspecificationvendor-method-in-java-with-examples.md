# 用 Java 打包 getSpecificationVendor()方法，示例

> 原文:[https://www . geesforgeks . org/package-getspecificationvendor-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getspecificationvendor-method-in-java-with-examples/)

[**java.lang.Package 类**](https://www.geeksforgeeks.org/java-lang-package-java/) 的 **getSpecificationVendor()** 方法用于获取该包的规格的厂商。方法以字符串形式返回包的规范供应商。
**语法:**

```
public String getSpecificationVendor()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法将包装的**规格供应商**作为字符串返回，如果已知的话。否则返回空值
下面的程序演示了 getSpecificationVendor()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getSpecificationVendor() method

public class Test {
    public static void main(String[] args)
    {

        // returns the Package
        // object for this package
        Package myPackage
            = Package.getPackage("java.lang");

        System.out.println(
            "Package represented"
            + " by myPackage: "
            + myPackage.toString());

        // Get the specification vendor
        // of myPackage using
        // getSpecificationVendor() method
        System.out.println(
            "Specification vendor"
            + " of myPackage: "
            + myPackage.getSpecificationVendor());
    }
}
```

**Output:** 

```
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Specification vendor of myPackage: Oracle Corporation
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getSpecificationVendor() method

public class Test {

    public static void main(String[] args)
    {

        // returns the Package
        // object for this package
        Package myPackage
            = Package.getPackage("java.io");

        System.out.println(
            "Package represented"
            + " by myPackage: "
            + myPackage.toString());

        // Get the specification vendor
        // of myPackage using
        // getSpecificationVendor() method
        System.out.println(
            "Specification vendor"
            + " of myPackage: "
            + myPackage.getSpecificationVendor());
    }
}
```

**Output:** 

```
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Specification vendor of myPackage: Oracle Corporation
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getspecification vendor–T4】