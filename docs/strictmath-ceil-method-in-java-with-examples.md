# Java 中的 StrictMath ceil()方法，带示例

> 原文:[https://www . geesforgeks . org/strict math-ceil-method-in-Java-with-examples/](https://www.geeksforgeeks.org/strictmath-ceil-method-in-java-with-examples/)

java.lang.StrictMath 类的所有方法:[集合 1](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/) 、[集合 2](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-2/)
**java . lang . strict math . ceil()**是 Java 中的一个内置方法，用于返回最小的双精度值，大于等于给定的双精度参数，等于一个整数。它产生了三个特殊的结果:

*   当给定的参数等于整数时，结果与参数相同。
*   当给定参数为 NaN、无穷大、正零或负零时，结果与参数相同。
*   当给定参数小于 0 且大于-1.0 时，结果为负 0。

**语法:**

```
public static double ceil(*double num*)
```

**参数:**该方法接受一个双类型的参数*数*，其上限值将被返回。
**返回值:**该方法返回最小的浮点值，该值最接近负无穷大，大于或等于给定参数，也等于整数。
**示例:**

```
Input: num = 2.7
Output: 3.0

Input: num = -8.7
Output: -8.0
```

下面的程序说明了 java.lang.StrictMath.ceil()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.ceil()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 8.7, num2 = 7.1, num3 = 3.5;

        // It returns ceiling value
        double cValue = StrictMath.ceil(num1);
        System.out.println("The Ceil value of "+
                             num1+" = " + cValue);

        cValue = StrictMath.ceil(num2);
        System.out.println("The Ceil value of "+
                             num2+" = " + cValue);

        cValue = StrictMath.ceil(num3);
        System.out.println("The Ceil value of "+
                             num3+" = " + cValue);
    }
}
```

**Output:** 

```
The Ceil value of 8.7 = 9.0
The Ceil value of 7.1 = 8.0
The Ceil value of 3.5 = 4.0
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.ceil()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = -8.7, num2 = -7.1, num3 = -3.5;

        // It returns ceiling value
        double cValue = StrictMath.ceil(num1);
        System.out.println("The Ceil value of "+
                             num1+" = " + cValue);

        cValue = StrictMath.ceil(num2);
        System.out.println("The Ceil value of "+
                             num2+" = " + cValue);

        cValue = StrictMath.ceil(num3);
        System.out.println("The Ceil value of "+
                             num3+" = " + cValue);
   }
}
```

**Output:** 

```
The Ceil value of -8.7 = -8.0
The Ceil value of -7.1 = -7.0
The Ceil value of -3.5 = -3.0
```