# Java 中的 StrictMath cos()方法，带示例

> 原文:[https://www . geesforgeks . org/strict math-cos-method-in-Java-with-examples/](https://www.geeksforgeeks.org/strictmath-cos-method-in-java-with-examples/)

java.lang.StrictMath 类的所有方法:[集 1](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/) 、[集 2](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-2/)
**java . lang . strict math . cos()**是 Java 中的一个内置方法，用于返回给定角度的余弦值。当给定的参数是 NaN 或无穷大时，该方法返回 NaN。
**语法:**

```java
public static double cos(*double num*)
```

**参数:**该方法接受双类型的一个参数*数*，指的是要返回余弦值的弧度角。
**返回值:**该方法返回参数的余弦值。
**示例:**

```java
Input: num = 62.0
Output: 0.6735071623235862

Input: num = 64.6
Output: -0.19607204956188945
```

下面的程序说明了 java.lang.StrictMath.cos()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.cos()
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double num1 = 0.0, num2= 1.0 , num3= 64.6;

    /* Returns trigonometric cosine of specified
    angle in radian*/
    double cosValue = StrictMath.cos(num1);
    System.out.println("The cosine of "+
                           num1+" = " + cosValue);

    cosValue = StrictMath.cos(num2);
    System.out.println("The cosine of "+
                           num2+" = " + cosValue);

    cosValue = StrictMath.cos(num3);
    System.out.println("The cosine of "+
                           num3+" = " + cosValue);}
}
```

**Output:** 

```java
The cosine of 0.0 = 1.0
The cosine of 1.0 = 0.5403023058681398
The cosine of 64.6 = -0.19607204956188945
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.cos()
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double num1= -62.0, num2 = 1.0;
        double num3= (45*(Math.PI))/180;

    /* It returns the  cosine of specified
    angle in radian*/
    double cosValue = StrictMath.cos(num1);
    System.out.println("The cosine of "+
                           num1+" = " + cosValue);
    cosValue = StrictMath.cos(num2);
    System.out.println("The cosine of "+
                           num2+" = " + cosValue);
    cosValue = StrictMath.cos(num3);
    System.out.println("The cosine of "+
                           num3+" = " + cosValue);}
}
```

**Output:** 

```java
The cosine of -62.0 = 0.6735071623235862
The cosine of 1.0 = 0.5403023058681398
The cosine of 0.7853981633974483 = 0.7071067811865476
```