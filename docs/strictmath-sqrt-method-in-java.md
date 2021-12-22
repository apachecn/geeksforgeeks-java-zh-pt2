# Java 中的 StrictMath sqrt()方法

> 原文:[https://www . geesforgeks . org/strict math-sqrt-method-in-Java/](https://www.geeksforgeeks.org/strictmath-sqrt-method-in-java/)

**java . lang . StrictMath . sqrt()**是 Java 中 strict math 类的一种内置方法，用于获取指定双精度值的精确舍入正平方根。

**语法:**

```java
public static double sqrt(*double num*)
```

**参数:**函数接受双类型的单参数*数*，其平方根由函数返回。

**返回值:**该方法返回*数*的正平方根。它还会产生一些特殊情况:

*   如果参数为 *NaN* 或小于*零*，则函数返回 *NaN*
*   当参数为正*无穷大*时，函数返回正*无穷大*。
*   如果参数为零，该函数将使用与参数相同的符号返回*零*
*   结果是最接近参数值的数学平方根的双精度值。

**示例:**

```java
Input: num = 25
Output: 5.0

Input: -729
Output: NaN

```

下面的程序说明了 java.lang.StrictMath.sqrt()方法的使用:

**程序 1:**

```java
// Java Program to illustrate
// java.lang.StrictMath.sqrt() function
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 289, num2 = -729;
        double num3 = 0.0, num4 = 547.87;

        // It returns the positive square root
        double sqrt_Value = StrictMath.sqrt(num1);
        System.out.println("square root = " + sqrt_Value);

        sqrt_Value = StrictMath.sqrt(num2);
        System.out.println("square root = " + sqrt_Value);

        sqrt_Value = StrictMath.sqrt(num3);
        System.out.println("square root = " + sqrt_Value);

        sqrt_Value = StrictMath.sqrt(num4);
        System.out.println("square root = " + sqrt_Value);
    }
}
```

**Output:**

```java
square root = 17.0
square root = NaN
square root = 0.0
square root = 23.406622994357814

```

**程序 2:**

```java
// Java Program to illustrate
// java.lang.StrictMath.sqrt() function
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 1160, num2 = -97;
        double num3 = -0.0, num4 = 144;
        double num5 = -72.18;

        // It returns the positive square root
        double sqrt_Value = StrictMath.sqrt(num1);
        System.out.println("square root = " + sqrt_Value);

        sqrt_Value = StrictMath.sqrt(num2);
        System.out.println("square root = " + sqrt_Value);

        sqrt_Value = StrictMath.sqrt(num3);
        System.out.println("square root = " + sqrt_Value);

        sqrt_Value = StrictMath.sqrt(num4);
        System.out.println("square root = " + sqrt_Value);

        sqrt_Value = StrictMath.sqrt(num5);
        System.out.println("square root = " + sqrt_Value);
    }
}
```

**Output:**

```java
square root = 34.058772731852805
square root = NaN
square root = -0.0
square root = 12.0
square root = NaN

```