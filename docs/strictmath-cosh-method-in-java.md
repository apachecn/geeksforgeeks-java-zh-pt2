# Java 中的 StrictMath cosh()方法

> 原文:[https://www . geesforgeks . org/strict math-cosh-method-in-Java/](https://www.geeksforgeeks.org/strictmath-cosh-method-in-java/)

**java . lang . strict math . cosh()**是 Java 中的一个内置方法，它返回给定双参数的双曲余弦值。

*   当参数为 NaN 时，该方法返回 NaN。
*   当参数为无穷大时，方法返回正无穷大。
*   当给定参数为 0.0 时，该方法返回 1.0。

**语法:**

```java
public static double cosh(*double num*)
```

**参数:**该方法接受一个双精度类型的参数*数*，其双曲余弦值将被返回。
**返回值:**该方法返回*数*的双曲余弦值。
**示例:**

```java
Input: num = 60.0
Output: 5.710036949078421E25

Input: num = 0.0
Output: 1.0
```

下面的程序说明了 java.lang.StrictMath.cosh()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.cosh()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 78.8, num2 = 0.0, num3 = 1.0;

        // It returns the hyperbolic cosine of
        // specified angle in radian
        double coshvalue = StrictMath.cosh(num1);
        System.out.println("The cosh of "+
                     num1+" = " + coshvalue);

        coshvalue = StrictMath.cosh(num2);
        System.out.println("The cosh of "+
                     num2+" = " + coshvalue);

        coshvalue = StrictMath.cosh(num3);
        System.out.println("The cosh of "+
                     num3+" = " + coshvalue);
    }
}
```

**Output:** 

```java
The cosh of 78.8 = 8.344016962852523E33
The cosh of 0.0 = 1.0
The cosh of 1.0 = 1.543080634815244
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.cosh()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = (30 * (Math.PI)) / 180;
        double num2 = 11.0, num3 = 45.0;

        // It returns the hyperbolic cosine of
        // angle in radian
        double coshvalue = StrictMath.cosh(num1);
        System.out.println("The cosh of "+
                     num1+" = " + coshvalue);

        coshvalue = StrictMath.cosh(num2);
        System.out.println("The cosh of "+
                     num2+" = " + coshvalue);

        coshvalue = StrictMath.cosh(num3);
        System.out.println("The cosh of "+
                     num3+" = " + coshvalue);   
    }
}
```

**Output:** 

```java
The cosh of 0.5235987755982988 = 1.1402383210764286
The cosh of 11.0 = 29937.070865949758
The cosh of 45.0 = 1.7467135528742547E19
```