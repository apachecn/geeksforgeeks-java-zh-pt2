# Java 中的 StrictMath rint()方法

> 原文:[https://www . geesforgeks . org/strict math-rint-method-in-Java/](https://www.geeksforgeeks.org/strictmath-rint-method-in-java/)

**rint()** 是 Java 中 [StrictMath 类的内置方法，用于获取值最接近自变量且等于整数的双精度值。它返回一个整数值，当两个整数的双精度值相等地接近给定参数的值时，该整数值是偶数。当参数值已经等于整数时，它返回与参数相同的值，当参数为 NaN 或无穷大或正零或负零时，它返回与参数相同的值。
**语法:**](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/)

```java
public static double rint(*double num*)
```

**参数:**该方法接受使用该方法转换的双类型单参数*数*。
**返回值:**该方法返回最接近的等于整数的浮点值。
**示例:**

```java
Input: num =72.2
Output: 72.0
```

下面的程序说明了 rint()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.rint()

import java.lang.*;

public class Geeks {
    public static void main(String[] args)
    {

        // Get a double number
        double num1 = 87.1;

        // Convert the double number using rint() method
        double rint_Value = StrictMath.rint(num1);

        // Print the result
        System.out.println(" The Integer value closest to "
                         + num1 + " = " + rint_Value);

        // Get a double number
        double num2 = 65.9;

        // Convert the double number using rint() method
        rint_Value = StrictMath.rint(num1);

        // Print the result
        System.out.println(" The Integer value closest to "
                         + num1 + " = " + rint_Value);
    }
}
```

**Output:** 

```java
The Integer value closest to 87.1 = 87.0 
The Integer value closest to 87.1 = 87.0
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.rint()

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // Get a double number
        double num1 = -65.5;

        // Convert the double number using rint() method
        double rint_Value = StrictMath.rint(num1);

        // Print the result
        System.out.println(" The Integer value closest to "
                         + num1 + " = " + rint_Value);

        // Get a double number
        double num2 = -42.7;

        // Convert the double number using rint() method
        rint_Value = StrictMath.rint(num1);

        // Print the result
        System.out.println(" The Integer value closest to "
                         + num1 + " = " + rint_Value);
    }
}
```

**Output:** 

```java
The Integer value closest to -65.5 = -66.0 
The Integer value closest to -65.5 = -66.0
```