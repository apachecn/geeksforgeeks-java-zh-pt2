# Java 中的 StrictMath acos()方法

> 原文:[https://www . geesforgeks . org/strict math-acos-method-in-Java/](https://www.geeksforgeeks.org/strictmath-acos-method-in-java/)

**Java . lang . strict math . acos()**是一个内置方法，它返回给定参数和角度的余弦值。返回的角度在 *0.0* 和*π*之间的范围内。
**注意:**如果自变量的绝对值大于 1 或者自变量本身是 NaN，那么结果也是 NaN。

**语法:**

```
public static double acos(*double num*)
```

**参数:**该方法接受一个参数*数*，该参数为双精度类型，指的是要返回余弦的圆弧。

**返回值:**该方法返回自变量的弧余弦。

**示例:**

```
Input: num = 0.45 
Output: 1.1040309877476002

Input: num = 8.9
Output: NAN

```

下面的程序说明了 java.lang.StrictMath.acos()方法:
**程序 1:** 为正数

```
// Java program to illustrate the
// java.lang.StrictMath.acos()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 0.65, num2 = 6.30;

        // It returns the arc cosine of a value
        double acosValue = StrictMath.acos(num1);
        System.out.println("The arc cosine value of "+
                             num1 + " = " + acosValue);

        acosValue = StrictMath.acos(num2);
        System.out.println("arc cosine value of "+
                             num2 + " = " + acosValue);
    }
}
```

**Output:**

```
The arc cosine value of 0.65 = 0.863211890069541
arc cosine value of 6.3 = NaN

```

**程序 2:** 为负数。

```
// Java program to illustrate the
// java.lang.StrictMath.acos()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = -0.65, num2 = -6.30;

        // It returns the arc cosine of a value
        double acosValue = StrictMath.acos(num1);
        System.out.println("The arc cosine value of "+
                             num1 + " = " + acosValue);

        acosValue = StrictMath.acos(num2);
        System.out.println("arc cosine value of "+
                             num2 + " = " + acosValue);
    }
}
```

**Output:**

```
The arc cosine value of -0.65 = 2.278380763520252
arc cosine value of -6.3 = NaN

```