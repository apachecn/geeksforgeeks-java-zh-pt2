# 用示例将 getName()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-getname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getname-method-in-java-with-examples/)

[**java.lang.Package 类**](https://www.geeksforgeeks.org/java-lang-package-java/) 的 **getName()** 方法用于获取此包的名称。方法以字符串形式返回包的名称。
**语法:**

```java
public String getName()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法将包的**名称**作为字符串返回。
下面的程序演示了 getName()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getName() method

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

        // Get the name of myPackage
        // using getName() method
        System.out.println("Name of myPackage: "
                           + myPackage.getName());
    }
}
```

**Output:** 

```java
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Name of myPackage: java.lang
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getName() method

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
        // using getName() method
        System.out.println("Name of myPackage: "
                           + myPackage.getName());
    }
}
```

**Output:** 

```java
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Name of myPackage: java.io
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getName–T4】