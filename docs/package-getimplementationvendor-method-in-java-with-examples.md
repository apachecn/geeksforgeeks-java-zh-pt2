# 用示例将 getImplementationVendor()方法用 Java 打包

> 原文:[https://www . geesforgeks . org/package-getimplementationvender-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getimplementationvendor-method-in-java-with-examples/)

[**java.lang.Package 类**](https://www.geeksforgeeks.org/java-lang-package-java/) 的**getImplementationVendor()**方法用于获取该包的实现的厂商。方法以字符串形式返回包的实现供应商。

**语法:**

```java
public String getImplementationVendor()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法将包的**实现供应商**作为字符串返回，如果知道的话。否则返回空值

下面的程序演示了 getImplementationVendor()方法。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getImplementationVendor() method

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

        // Get the implementation vendor of myPackage
        // using getImplementationVendor() method
        System.out.println(
            "Implementation vendor of myPackage: "
            + myPackage.getImplementationVendor());
    }
}
```

**Output:** 

```java
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Implementation vendor of myPackage: N/A
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getImplementationVendor() method

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
        // using getImplementationVendor() method
        System.out.println(
            "Implementation vendor of myPackage: "
            + myPackage.getImplementationVendor());
    }
}
```

**Output:** 

```java
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Implementation vendor of myPackage: N/A
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getImplementationVendor–T4】