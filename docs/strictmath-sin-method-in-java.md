# Java 中的 StrictMath sin()方法

> 原文:[https://www . geesforgeks . org/strict math-sin-method-in-Java/](https://www.geeksforgeeks.org/strictmath-sin-method-in-java/)

**java . lang . strict math . sin()**是 Java 中的一个内置函数，它返回一个角度的三角正弦值。

**语法:**

```java
public static double sin(*double ang*)
```

**参数:**该函数接受单个参数*和*，这是一个双变量，表示一个角度(以弧度为单位)，该函数将返回其三角正切值。

**返回值:**该方法返回作为参数传递给函数的角度的正弦值。考虑以下情况:

*   如果参数是 *NaN* 或*无穷大*，则函数返回 *NaN* 。
*   如果参数为*零*，则函数返回符号与参数相同的*零*。

**例:**

```java
Input : ang = 0.5235987755982988(30 degree)
Output : 0.49999999999999994

Input : ang = 0.7853981633974483(45 degree)
Output : 0.7071067811865475

```

下面的程序说明了 java 中 java.lang.StrictMath.sin()函数的工作原理:

**程序 1:**

```java
// Java Program to illustrate sin()
import java.io.*;
import java.math.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        double ang = (60 * Math.PI) / 180;

        // Display the trigonometric sine of the angle
        System.out.println("Sine value of 60 degrees : "
                                 + StrictMath.sin(ang));
    }
}
```

**输出:**

```java
Sine value of 60 degrees : 0.8660254037844386

```

**程序二:**

```java
// Java Program to illustrate sin()
import java.io.*;
import java.math.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        double ang = 77.128;
        // Convert the angle to its equivalent radian
        double rad = StrictMath.toRadians(ang);
        System.out.println(rad);

        // Display the trigonometric sine of the angle
        System.out.println("Sine value of 77.128 degrees : "
                                     + StrictMath.sin(rad));
    }
}
```

**输出:**

```java
1.3461375454781863
Sine value of 77.128 degrees : 0.9748701783788553

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/strict math . html # sin()](https://docs.oracle.com/javase/8/docs/api/java/lang/StrictMath.html#sin-double-)