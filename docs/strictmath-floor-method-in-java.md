# Java 中的 StrictMath floor()方法

> 原文:[https://www . geesforgeks . org/strict math-floor-method-in-Java/](https://www.geeksforgeeks.org/strictmath-floor-method-in-java/)

**Java . lang . strict math . floor()**是一个内置方法，它返回最大的双精度值，小于或等于给定的参数，等于整数值。

*   当给定的参数等于整数时，结果与参数相同。
*   当给定参数为 NaN、无穷大、正零或负零时，结果与参数相同。

**语法:**

```java
public static double floor(*double num*)
```

**参数:**该方法接受一个参数*数*，该参数为双型。
**返回值:**该方法返回最大值，该值最接近于正无穷大，小于或等于自变量且等于整数。
**示例:**

```java
Input: num = 9.6
Output: 9.0

Input: num = -7.8
Output: -8.0
```

下面的程序说明了 java.lang.StrictMath.floor()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
//java.lang.StrictMath.floor()

import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double num1 = 7.8, num2 = 1.4 ;

    double fValue = StrictMath.floor(num1);
    System.out.println("The floor value of "+
                             num1+" = " + fValue);

    fValue = StrictMath.floor(num2);
    System.out.println("The floor value of "+
                             num2+" = " + fValue);
}
}
```

**Output:** 

```java
The floor value of 7.8 = 7.0
The floor value of 1.4 = 1.0
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
//java.lang.StrictMath.floor()

import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double num1 = -7.8, num2 = -1.4 ,num3 = 0.1 ;

    double fValue = StrictMath.floor(num1);
    System.out.println("The floor value of "+
                             num1+" = " + fValue);

    fValue = StrictMath.floor(num2);
    System.out.println("The floor value of "+
                             num2+" = " + fValue);

    fValue = StrictMath.floor(num3);
    System.out.println("The floor value of "+
                             num3+" = " + fValue);

}
}
```

**Output:** 

```java
The floor value of -7.8 = -8.0
The floor value of -1.4 = -2.0
The floor value of 0.1 = 0.0
```