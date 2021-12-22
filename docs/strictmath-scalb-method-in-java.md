# Java 中的 StrictMath scalb()方法

> 原文:[https://www . geesforgeks . org/strict math-scalb-method-in-Java/](https://www.geeksforgeeks.org/strictmath-scalb-method-in-java/)

1.  The **scalb(*double num, int scale*)** is an inbuilt method of StrictMath class in Java which is used to calculate *num* * 2^*scale* and rounded as performed by a single correctly rounded floating point multiplied to a member of the double value argument.
    *   当结果的指数在**倍之间时，结果计算准确。最小指数**和**加倍。最大指数**。
    *   当结果的指数大于**倍时，返回无穷大。最大指数**。
    *   当结果低于正常值时，正确性可能会丧失，这意味着当 scalb( *num，scale* )低于正常值时，scalb(scalb( *num，scale* )，-scale)可能不等于 *num* 。
    *   当 *num* 为 NaN 时，结果为 NaN
    *   当*数*为无穷大时，结果是*数*的同一个符号为无穷大
    *   当*数*为零时，结果将是相同符号的零。

    **语法:**

    ```java
    public static double scalb(*double num, int scale*)
    ```

    **参数:**该方法接受两个参数:

    *   *num* :这是双数型，指的是要按 2 的幂进行缩放的数。
    *   *scalb* :这是整数类型，指的是用来缩放*数*的 2 的幂。

    **返回值:**该方法返回*数值* × 2^ *刻度*。

    **示例:**

    ```java
    Input: num = 7
           scalb = 2
    Output: 28

    ```

    下面的程序说明了 java.lang.StrictMath.scalb()方法。

    ```java
    // Java praogram to illustrate the
    // java.lang.StrictMath.scalb() 
    import java.lang.*;

    public class Geeks {

    public static void main(String[] args) {

        double num1 = 12 , num2 = -7.2, num3 = 0.0;
        int scalb = 2;

        double scalb_Value = StrictMath.scalb(num1, scalb); 
        System.out.println("Output = "+scalb_Value);

        scalb_Value = StrictMath.scalb(num2, scalb); 
        System.out.println("Output = " +scalb_Value);

        scalb_Value = StrictMath.scalb(num3, scalb); 
        System.out.println("Output = "+scalb_Value);
    }
    }
    ```

    **Output:**

    ```java
    Output = 48.0
    Output = -28.8
    Output = 0.0

    ```

2.  The **scalb(float num, int scale)** is the inbuilt method of StrictMath class in Java to calculate *num* * 2^*scale* and rounded as performed by a single correctly rounded floating point multiplied to a member of the float value argument.
    *   当结果的指数在 **Float 之间时，结果计算准确。最小指数**和**浮动。最大指数**。
    *   当结果的指数大于**浮点时，返回无穷大。最大指数**。
    *   当结果低于正常值时，正确性可能会丧失，这意味着当 scalb( *num，scale* )低于正常值时，scalb(scalb( *num，scale* )，-scale)可能不等于 *num* 。
    *   当 *num* 为 NaN 时，结果为 NaN
    *   当*数*为无穷大时，结果是*数*的同一个符号为无穷大
    *   当*数*为零时，结果将是相同符号的零。

    **语法:**

    ```java
    public static float scalb(*float num, int scale*)
    ```

    **参数:**该方法接受两个参数:

    *   *num* :这是浮点型的，指的是要用 2 的幂来缩放的数字。
    *   *scalb* :这是整数类型，指的是用来缩放*数*的 2 的幂。

    **返回值:**该方法返回*数值* × 2^ *刻度*。

    **示例:**

    ```java
    Input: num = 2.5f
           scalb = 4
    Output: 40.0

    ```

    下面的程序说明了 java.lang.StrictMath.scalb()方法。

    ```java
    // Java praogram to illustrate the
    // java.lang.StrictMath.scalb() 
    import java.lang.*;

    public class Geeks {

    public static void main(String[] args) {

        float num1 = 8.3f, num2 = -4.2f, num3 = 0.0f;
        int scalb = 3;

        float scalb_Value = StrictMath.scalb(num1, scalb); 
        System.out.println("Output = "+scalb_Value);

        scalb_Value = StrictMath.scalb(num2, scalb); 
        System.out.println("Output = " +scalb_Value);

        scalb_Value = StrictMath.scalb(num3, scalb); 
        System.out.println("Output = "+scalb_Value);
    }
    }
    ```

    **Output:**

    ```java
    Output = 66.4
    Output = -33.6
    Output = 0.0

    ```