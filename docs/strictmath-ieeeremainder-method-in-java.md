# Java 中的 StrictMath IEEEremainder()方法

> 原文:[https://www . geesforgeks . org/strict math-ieeereminder-method-in-Java/](https://www.geeksforgeeks.org/strictmath-ieeeremainder-method-in-java/)

Java . lang . StrictMath . ieeereminder()是 strict math 类的内置方法，用于对 IEEE 754 标准规定的给定两个参数执行余数运算。余数值在数学上等于![num1 - num2 * rem  ](img/d6614773717cf454ce7c5100308b9257.png "Rendered by QuickLaTeX.com")，其中 *rem* 是最接近商![num1 / num2  ](img/ce786e73ae129176e23c4d6aca7eff1f.png "Rendered by QuickLaTeX.com")精确数学值的数学整数，当两个数学整数相等接近![num1 / num2  ](img/ce786e73ae129176e23c4d6aca7eff1f.png "Rendered by QuickLaTeX.com")时，n 是偶数。它产生了两个特殊的结果:

*   余数为零时，它的符号与第一个参数的符号相同。
*   当任一参数为 NaN，或 *num1* 为无穷大，或 *num2* 为正或负零时，返回 NaN。
*   结果与 *num1* 有限而 *num2* 无限时 *num1* 相同。

**语法:**

```java
public static double IEEEremainder(double num1, double num2)
```

**参数:**该方法接受两个参数:

*   *num1:* 这是双数型，也就是被除数。
*   *num2* 这是除数的双重类型 als。

**返回值:**当 num1 除以 num2 时，该方法返回余数。
**例:**

```java
Input: 
num1 = 100.61d
num2 = 5.32d

Output: -0.47000000000000597
```

下面的程序说明了 Java . lang . strict math . ieeereminder()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// Java.lang.StrictMath.IEEEremainder()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 5651.51d, num2 = 61.79d;

        // It  returns the remainder value
        double remain_val = StrictMath.IEEEremainder(num1, num2);
        System.out.println("Remainder value of "+num1+" & "+num2
                                            +" = " + remain_val);
    }
}
```

**Output:** 

```java
Remainder value of 5651.51 & 61.79 = 28.620000000000296
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// Java.lang.StrictMath.IEEEremainder()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {
        /* Here  num1 is finite and num2 is infinite so
     the result is the same as the num1 */
        double num1 = 70.55d, num2 = (1.0) / (0.0);

        double remain_val = StrictMath.IEEEremainder(num1, num2);
        System.out.println("Remainder value of "+num1+" & "+num2
                                            +" = " + remain_val);
    }
}
```

**Output:** 

```java
Remainder value is = 70.55
```