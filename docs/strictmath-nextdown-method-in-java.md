# Java 中的 StrictMath nextDown()方法

> 原文:[https://www . geesforgeks . org/strict math-next down-method-in-Java/](https://www.geeksforgeeks.org/strictmath-nextdown-method-in-java/)

### 下一个数字

**nextDown(double num)** 是 Java 中 [StrictMath 类的内置方法，用于获取负无穷大方向上与 *num* 相邻的浮点值。当参数是 NaN 时，结果是 NaN。当*数*为负无穷大时，返回负无穷大。结果是双倍。参数为零时的最小值。nextDown()方法相当于 nextAfter( *num，Double。NEGATIVE_INFINITY* )但是 nextDown()比它的等价的 nextAfter 调用运行得更快。](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/)

**语法:**

```
public static double nextDown(*double num*)
```

**参数:**该方法接受双类型的一个参数*数*，该参数为起始浮点值。

**返回值:**该方法返回更接近负无穷大的相邻浮点值。

**示例:**

```
Input: num = 7.16
Output: 7.159999999999999
```

下面的程序说明了 nextDown()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// Java.lang.StrictMath.nextDown() Method

import java.lang.*;

public class Geeks {
    public static void main(String[] args)
    {

        // Get a double number
        double num1 = 62.9;

        // Get the floating-point value adjacent to num
        double nextDown_Value = StrictMath.nextDown(num1);

        // Print the result
        System.out.println("The Next down value of "
                           + num1 + " = " + nextDown_Value);

        // Get a double number
        double num2 = 16.6226;

        // Get the floating-point value adjacent to num
        nextDown_Value = StrictMath.nextDown(num2);

        // Print the result
        System.out.println("The Next down value of "
                           + num2 + " = " + nextDown_Value);

        // Get a double number
        double num3 = 0.0;

        // Get the floating-point value adjacent to num
        nextDown_Value = StrictMath.nextDown(num3);

        // Print the result
        System.out.println("The Next down value of "
                           + num3 + " = " + nextDown_Value);
    }
}
```

**Output:** 

```
The Next down value of 62.9 = 62.89999999999999
The Next down value of 16.6226 = 16.622599999999995
The Next down value of 0.0 = -4.9E-324
```

### 下一个向下(浮点数)

**nextDown(float num)** 是 Java 中 StrictMath 类的内置方法，用于获取负无穷大方向上与 *num* 相邻的浮点值。当参数是 NaN 时，结果是 NaN。当*数*为负无穷大时，返回负无穷大。结果是“浮动”。参数为零时的最小值。nextDown()方法相当于 nextAfter( *num，Float。NEGATIVE_INFINITY* )但是 nextDown()比它的等价的 nextAfter 调用运行得更快。

**语法:**

```
public static float nextDown(*float num*)
```

**参数:**该方法接受一个浮点类型的参数*数*，该参数为起始浮点值。

**返回值:**该方法返回更接近负无穷大的相邻浮点值。

**示例:**

```
Input: num = 1.2f
Output: 1.1999999
```

下面的程序说明了方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// Java.lang.StrictMath.nextDown() Method

import java.lang.*;

public class Geeks {
    public static void main(String[] args)
    {

        // Get a float number
        float num1 = 16.622f;

        // Get the floating-point value adjacent to num
        float nextDown_Value = StrictMath.nextDown(num1);

        // Print the result
        System.out.println("The Next down value of "
                           + num1 + " = " + nextDown_Value);

        // Get a float number
        float num2 = 91.11f;

        // Get the floating-point value adjacent to num
        nextDown_Value = StrictMath.nextDown(num2);

        // Print the result
        System.out.println("The Next down value of "
                           + num2 + " = " + nextDown_Value);

        // Get a float number
        float num3 = 0.0f;

        // Get the floating-point value adjacent to num
        nextDown_Value = StrictMath.nextDown(num3);

        // Print the result
        System.out.println("The Next down value of "
                           + num3 + " = " + nextDown_Value);
    }
}
```

**Output:** 

```
The Next down value of 16.622 = 16.621998
The Next down value of 91.11 = 91.10999
The Next down value of 0.0 = -1.4E-45
```