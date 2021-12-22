# Java 中的 StrictMath cbrt()方法

> 原文:[https://www . geesforgeks . org/strict math-cbrt-method-in-Java/](https://www.geeksforgeeks.org/strictmath-cbrt-method-in-java/)

**java . lang . strict math . cbrt()**是 Java 中的一个内置方法，用于返回给定双精度值的立方根。该方法显示了三个特殊结果:

*   当给定的参数为零时，结果是一个零，其符号与参数相同。
*   当自变量为无穷大时，结果为无穷大，自变量符号相同。
*   当给定的参数是 NaN 时，结果是 NaN。

**语法:**

```java
public static double cbrt(*double num*)
```

**参数:**该方法接受一个参数*数*，该参数为要求求立方根的双数型。
**返回值:**该方法返回*数*的立方根。
下面的程序说明了 java.lang.StrictMath.cbrt()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.cbrt()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double val1 = 8.05, val2 = 27, val3 = 0;

        // It returns the cube root of a double value
        double cbrtvalue = StrictMath.cbrt(val1);
        System.out.println("Cube root of "+val1+
                                  " = " + cbrtvalue);

        cbrtvalue = StrictMath.cbrt(val2);
        System.out.println("Cube root of "+val2+
                                  " = " + cbrtvalue);

        cbrtvalue = StrictMath.cbrt(val3);
        System.out.println("Cube root of "+val3+
                                  " = " + cbrtvalue);

    }
}
```

**Output:** 

```java
Cube root of 8.05 = 2.0041580161269152
Cube root of 27.0 = 3.0
Cube root of 0.0 = 0.0
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.cbrt()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double val1 = -8.05, val2 = 128, val3 = 0;

        // It returns the cube root of a double value
        double cbrtvalue = StrictMath.cbrt(val1);
        System.out.println("Cube root of "+val1+
                                  " = " + cbrtvalue);

        cbrtvalue = StrictMath.cbrt(val2);
        System.out.println("Cube root of "+val2+
                                  " = " + cbrtvalue);

        cbrtvalue = StrictMath.cbrt(val3);
         System.out.println("Cube root of "+val3+
                                  " = " + cbrtvalue);

    }
}
```

**Output:** 

```java
Cube root of -8.05 = -2.0041580161269152
Cube root of 128.0 = 5.039684199579493
Cube root of 0.0 = 0.0
```