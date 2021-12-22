# Java 中的 StrictMath ulp()方法，带示例

> 原文:[https://www . geesforgeks . org/strict math-ulp-method-in-Java-with-examples/](https://www.geeksforgeeks.org/strictmath-ulp-method-in-java-with-examples/)

### ulp(双数字)

**ulp(double num)** 是 java 中 StrictMath 类的一个内置方法，用于获取给定参数的 ulp 的大小。一个双数值的 **ulp** 是这个浮点值和下一个更大的双数值之间的正距离。
一些特殊情况是:

*   结果是 **NaN** ，如果参数是 NaN。
*   结果是**正无穷大**，如果自变量是正无穷大或负无穷大。
*   结果是**翻倍。如果参数为正或负零，则为最小值**。
*   如果参数是双精度的，结果等于 **2^971** 。最大值。

**语法:**

```
public static double ulp(double num)
```

**参数:**该方法接受一个双精度类型的参数**数**，即要返回 ulp 的浮点值。
**返回值:**ulp 方法返回参数的 ulp 的**大小。
**示例:****

```
Input: num = 5.7
Output: 8.881784197001252E-16

Input: num = 0.0
Output: 4.9E-324
```

下面的程序说明了 java.lang.StrictMath.ulp()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.ulp()

import java.lang.*;

public class GFG {
    public static void main(String[] args)
    {

        double num1 = 9.7, num2 = 4.9;

        // Get the size of an ulp of the argument
        // using ulp() method
        double ulp_Value = StrictMath.ulp(num1);

        // Print the size of the ulp
        System.out.println(" The Size of ulp of "
                           + num1 + " = "
                           + ulp_Value);

        // Get the size of an ulp of the argument
        // using ulp() method
        ulp_Value = StrictMath.ulp(num2);

        // Print the size of the ulp
        System.out.println(" The Size of ulp of "
                           + num2 + " = "
                           + ulp_Value);
    }
}
```

**Output:** 

```
 The Size of ulp of 9.7 = 1.7763568394002505E-15
 The Size of ulp of 4.9 = 8.881784197001252E-16
```

### ulp(浮点数值)

**ulp(float num)** 是 java 中 StrictMath 类的一个内置方法，用于获取给定参数的 ulp 的大小。浮点值的 **ulp** 是该浮点值和下一个幅度较大的浮点值之间的正距离。
一些特殊情况是:

*   结果是 **NaN** ，如果参数是 NaN。
*   结果是**正无穷大**，如果自变量是正无穷大或负无穷大。
*   结果是**浮动。如果参数为正或负零，则为最小值**。
*   如果参数为 Float，则结果等于 **2^104** 。最大值。

**语法:**

```
public static float ulp(float num)
```

**参数:**该方法接受浮点类型的一个参数**数**，即要返回 ulp 的浮点值。
**返回值:**ulp 方法返回参数的 ulp 的**大小。
**示例:****

```
Input: num = 5.7
Output: 8.881784197001252E-16

Input: num = 0.0
Output: 4.9E-324
```

下面的程序说明了 java.lang.StrictMath.ulp()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.ulp()

import java.lang.*;

public class GFG {
    public static void main(String[] args)
    {

        float num1 = 2.7f, num2 = -4.5f;

        // Get the size of an ulp of the argument
        // using ulp() method
        float ulp_Value = StrictMath.ulp(num1);

        // Print the size of the ulp
        System.out.println(" The Size of ulp of "
                           + num1 + " = "
                           + ulp_Value);

        // Get the size of an ulp of the argument
        // using ulp() method
        ulp_Value = StrictMath.ulp(num2);

        // Print the size of the ulp
        System.out.println(" The Size of ulp of "
                           + num2 + " = "
                           + ulp_Value);
    }
}
```

**Output:** 

```
 The Size of ulp of 2.7 = 2.3841858E-7
 The Size of ulp of -4.5 = 4.7683716E-7
```