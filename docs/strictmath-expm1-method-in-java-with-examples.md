# Java 中的 StrictMath expm1()方法，带示例

> 原文:[https://www . geesforgeks . org/strict math-ex pm1-method-in-Java-with-examples/](https://www.geeksforgeeks.org/strictmath-expm1-method-in-java-with-examples/)

java.lang.StrictMath.expm1()是 java 中的一个内置方法，用于返回给定值 *num* 的*指数 e^num -1* 。该方法产生四种不同的情况:

*   当给定的参数是 NaN 时，该方法返回 NaN。
*   当参数为正无穷大时，结果为正无穷大。
*   当参数为负无穷大时，结果为负无穷大。
*   对于 0，方法返回与参数符号相同的 0。

**语法:**

```java
public static double expm1(*double num*)
```

**参数:**该方法接受一个双型参数*数*，指的是要进行指数运算的值。
**返回值:**该方法将返回*e<sup>num</sup>–1*运算的结果。
**示例:**

```java
Input: num = (1.0/0.0)
Output: Infinity

Input: 32.2
Output: 9.644557735961714E13
```

下面的程序说明了 java.lang.StrictMath.expm1()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.expm1()
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double num1 = 0.0, num2 = -(1.0/0.0);
        double num3 = (1.0/0.0), num4 = 32.2;

    /*It  returns e^num - 1 */
    double eValue = StrictMath.expm1(num1);
    System.out.println("The expm1 Value of "+
                              num1+" = "+eValue);

    eValue = StrictMath.expm1(num2);
    System.out.println("The expm1 Value of "+
                              num2+" = "+eValue);

    eValue = StrictMath.expm1(num3);
    System.out.println("The expm1 Value of "+
                              num3+" = "+eValue);

    eValue = StrictMath.expm1(num4);
    System.out.println("The expm1 Value of "+
                              num4+" = "+eValue);}
}
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.expm1()
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double num1 = 2.0 , num2 = -51.8;
        double num3 = 61.0, num4 = -32.2;

    /*It  returns e^num - 1 */
    double eValue = StrictMath.expm1(num1);
    System.out.println("The expm1 Value of "+
                              num1+" = "+eValue);

    eValue = StrictMath.expm1(num2);
    System.out.println("The expm1 Value of "+
                              num2+" = "+eValue);

    eValue = StrictMath.expm1(num3);
    System.out.println("The expm1 Value of "+
                              num3+" = "+eValue);

    eValue = StrictMath.expm1(num4);
    System.out.println("The expm1 Value of "+
                              num4+" = "+eValue);
}
}
```