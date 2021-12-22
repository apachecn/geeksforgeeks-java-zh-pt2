# Java 中的 StrictMath pow()方法

> 原文:[https://www . geesforgeks . org/strict math-pow-method-in-Java/](https://www.geeksforgeeks.org/strictmath-pow-method-in-java/)

**Java . lang . StrictMath . pow()**是 strict math 类的一种内置方法，用于查找幂值，即一个参数的值与另一个参数的幂的乘积。数学上它指的是![a^b  ](img/c6c720ff0724f286a46166db53c4f72c.png "Rendered by QuickLaTeX.com")。它产生了三个特殊的结果:

*   当一个参数为 NaN，另一个参数为非零参数或 NaN 时，该方法返回 NaN。
*   当第二个参数为 1.0 时，方法返回与第一个参数相同的值。
*   当第二个参数为正或负零时，该方法返回 1.0。

**语法:**

```
public static double pow(*double num1, double num2*)
```

**参数:**该方法接受两个参数:

*   *num1:* 此为双型，指的是碱基。
*   *num2:* 此为双型，指指数。

**返回值:**该方法返回 num1^num2.运算的值
**例:**

```
Input: num1 = 6
       num2 = 4
Output: 1296.0

Input: num1 = 5
       num2 = 2
Output: 25.0
```

下面的程序说明了 java.lang.StrictMath.pow()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.pow()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 12, num2 = 6;

        // It returns num1 to the power num2
        double pow_Value = StrictMath.pow(num1, num2);
        System.out.print(num1 + " to the power of " +
                                        num2 + " = ");
        System.out.println(pow_Value);

        double pow_Value1 = StrictMath.pow(num1, 0);
        double pow_Value2 = StrictMath.pow(num1, 0);
        System.out.println(num1+" raised to the"+
                        " power 0 = " + pow_Value1);
        System.out.println(num2+" raised to the"+
                        " power 0 = " + pow_Value2);
    }
}
```

**Output:** 

```
12.0 to the power of 6.0 = 2985984.0
12.0 raised to the power 0 = 1.0
6.0 raised to the power 0 = 1.0
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.pow()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 4.7, num2 = 2.5;

        // It returns num1 to the power num2
        double pow_Value = StrictMath.pow(num1, num2);
        System.out.print(num1 + " to the power of " +
                                        num2 + " = ");
        System.out.println(pow_Value);
    }
}
```

**Output:** 

```
4.7 to the power of 2.5 = 47.88997880559147
```