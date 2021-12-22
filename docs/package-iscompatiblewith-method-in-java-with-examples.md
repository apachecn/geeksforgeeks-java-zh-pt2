# Java 中的 Package isCompatibleWith()方法，示例

> 原文:[https://www . geesforgeks . org/package-is compatiblewith-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-iscompatiblewith-method-in-java-with-examples/)

[**java.lang.Package 类**](https://www.geeksforgeeks.org/java-lang-package-java/) 的 **isCompatibleWith()** 方法用于检查该包的规范版本是否与指定版本兼容。方法以布尔值的形式返回结果。
**语法:**

```
public boolean isCompatibleWith(String desiredVersion)
```

**参数:**该方法接受一个参数 **desiredVersion** ，该参数是要检查兼容性的版本。
**返回值:**该方法将结果作为**布尔值**返回。
以下程序演示了 isCompatibleWith()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isCompatibleWith() method

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

        String desiredVersion = "1.5";

        // check if this package is compatible with or not
        // using isCompatibleWith() method
        System.out.println(
            "Is this package compatible with or not: "
            + myPackage.isCompatibleWith(desiredVersion));
    }
}
```

**Output:** 

```
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Is this package compatible with or not: true
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isCompatibleWith() method

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

        String desiredVersion = "1.0";

        // check if this package is compatible with or not
        // using isCompatibleWith() method
        System.out.println(
            "Is this package compatible with or not: "
            + myPackage.isCompatibleWith(desiredVersion));
    }
}
```

**Output:** 

```
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Is this package compatible with or not: true
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # is compatiblewith-Java . lang . string-T4】