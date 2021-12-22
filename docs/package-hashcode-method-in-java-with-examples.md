# 用示例将 hashCode()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-hashcode-method-in-java-with-examples/)

**[java.lang.Package 类](https://www.geeksforgeeks.org/java-lang-package-java/)** 的 **hashCode()** 方法用来获取这个包实例的 hashCode 值。方法以整数值的形式返回哈希值。

**语法:**

```java
public int hashCode()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法将哈希值作为**整数值**返回。

下面的程序演示了 hashCode()方法。

**例 1:**

```java
// Java program to demonstrate
// hashCode() method

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

        // get the hashCode value of this package
        // using hashCode() method
        System.out.println(
            "hashCode value: "
            + myPackage.hashCode());
    }
}
```

**输出:**

```java
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
hashCode value: -888658374

```

**例 2:**

```java
// Java program to demonstrate
// hashCode() method

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

        // get the hashCode value of this package
        // using hashCode() method
        System.out.println(
            "hashCode value: "
            + myPackage.hashCode());
    }
}
```

**输出:**

```java
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
hashCode value: -1819917198

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#hashCode--)