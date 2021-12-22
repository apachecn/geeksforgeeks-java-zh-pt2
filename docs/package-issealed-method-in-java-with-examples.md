# 用示例将 isSealed()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-issealed-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-issealed-method-in-java-with-examples/)

[**java.lang.Package 类**](https://www.geeksforgeeks.org/java-lang-package-java/) 的 **isSealed()** 方法用于检查该包裹是否密封。方法以布尔值的形式返回结果。
**语法:**

```java
public boolean isSealed()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法将结果作为**布尔值**返回。
下面的程序演示了 isSealed()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// isSealed() method

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

        // check if this package is sealed or not
        // using isSealed() method
        System.out.println(
            "Is this package sealed or not: "
            + myPackage.isSealed());
    }
}
```

**Output:** 

```java
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Is this package sealed or not: false
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// isSealed() method

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

        // check if this package is sealed or not
        // using isSealed() method
        System.out.println(
            "Is this package sealed or not: "
            + myPackage.isSealed());
    }
}
```

**Output:** 

```java
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Is this package sealed or not: false
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # isSealed–T4】