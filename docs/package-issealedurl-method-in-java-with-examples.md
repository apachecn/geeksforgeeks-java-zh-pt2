# 用示例打包 Java 中的隐藏(网址)方法

> 原文:[https://www . geesforgeks . org/package-issaledurl-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-issealedurl-method-in-java-with-examples/)

[**java.lang.Package 类**](https://www.geeksforgeeks.org/java-lang-package-java/) 的 **isSealed(URL)** 方法用于针对指定的 URL 检查该包裹是否密封。方法以布尔值的形式返回结果。
**语法:**

```
public boolean isSealed(URL url)
```

**参数:**此方法不接受任何参数。
**返回值:**该方法将结果作为**布尔值**返回。
下面的程序演示了 isSealed(网址)方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isSealed(URL) method

import java.net.*;

public class Test {
    public static void main(String[] args)
        throws MalformedURLException
    {

        // returns the Package
        // object for this package
        Package myPackage
            = Package.getPackage("java.lang");

        System.out.println(
            "Package represented by myPackage: "
            + myPackage.toString());

        URL url
            = new URL("https://www.geeksforgeeks.org");

        // check if this package is sealed or not
        // using isSealed(URL) method
        System.out.println(
            "Is this package sealed or not: "
            + myPackage.isSealed(url));
    }
}
```

**Output:** 

```
Package represented by myPackage: package java.lang, Java Platform API Specification, version 1.8
Is this package sealed or not: false
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isSealed(URL) method

import java.net.*;

public class Test {
    public static void main(String[] args)
        throws MalformedURLException
    {

        // returns the Package
        // object for this package
        Package myPackage
            = Package.getPackage("java.io");

        System.out.println(
            "Package represented by myPackage: "
            + myPackage.toString());

        URL url
            = new URL("http://www.gfg.org");

        // check if this package is sealed or not
        // using isSealed(URL) method
        System.out.println(
            "Is this package sealed or not: "
            + myPackage.isSealed(url));
    }
}
```

**Output:** 

```
Package represented by myPackage: package java.io, Java Platform API Specification, version 1.8
Is this package sealed or not: false
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # isSealed–T4】