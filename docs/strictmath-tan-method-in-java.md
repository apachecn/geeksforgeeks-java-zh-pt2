# Java 中的 StrictMath tan()方法

> 原文:[https://www . geesforgeks . org/strict math-tan-method-in-Java/](https://www.geeksforgeeks.org/strictmath-tan-method-in-java/)

**java . lang . strict math . tan()**是 Java 中的一个内置函数，它返回一个角度的三角正切值。

**语法:**

```java
public static double tan*(*double ang*)*
```

**参数:**该函数接受单个参数*和*，这是一个双变量，表示一个角度(以弧度为单位)，其三角正切值将由该函数返回。

**返回值:**该方法返回作为参数传递给函数的角度的正切值。它会产生特殊情况:

*   如果参数是 *NaN* 或*无穷大*，则该方法返回 *NaN* 。
*   如果参数为零，则结果为零，符号与参数相同。

**例:**

```java
Input : ang = 0.5235987755982988(30 degree)
Output : 0.5773502691896257

Input : ang = 0.7853981633974483(45 degree)
Output : 0.9999999999999999

```

下面的程序说明了 java 中的 java.lang.StrictMath.tan()函数:

**程序 1:**

```java
// Java Program to illustrate 
// StrictMath.tan() function

import java.io.*;
import java.math.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        double ang = (60 * Math.PI) / 180;

        // Display the trigonometric tangent of the angle
        System.out.println("tangent value of 60 degrees : "
                           + StrictMath.tan(ang));
    }
}
```

**输出:**

```java
tangent value of 60 degrees : 1.7320508075688767

```

**程序二:**

```java
// Java Program to illustrate 
// StrictMath.tan() function

import java.io.*;
import java.math.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        double ang = 77.128;
        // Convert the angle to its equivalent radian
        double rad = StrictMath.toRadians(ang);

        // Display the trigonometric tangent of the angle
        System.out.println("tangent value of 77.128 degrees : "
                           + StrictMath.tan(rad));
    }
}
```

**输出:**

```java
tangent value of 77.128 degrees : 4.376055350774854

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/strict math . html # tan()](https://docs.oracle.com/javase/8/docs/api/java/lang/StrictMath.html#tan-double-)