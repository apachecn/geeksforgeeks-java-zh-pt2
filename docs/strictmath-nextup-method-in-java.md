# Java 中的 StrictMath nextUp()方法

> 原文:[https://www . geesforgeks . org/strict math-nextup-method-in-Java/](https://www.geeksforgeeks.org/strictmath-nextup-method-in-java/)

1.  The **nextUp(*double num*)** is an inbuilt method of StrictMath class in Java which is used to get the float value that is contiguous to *num* in the direction of positive infinity. The nextup() method is equivalent to nextAfter(*num, Double.POSITIVE_INFINITY*) but nextup() runs faster than nextAfter().

    **语法:**

    ```
    public static double nextUp(*double num*)
    ```

    **参数:**该方法接受双类型的一个参数*数*，该参数为起始浮点值。

    **返回值:**该方法返回接近正无穷大的相邻浮点值。它有三种特殊情况:

    *   当参数是 NaN 时，结果是 NaN。
    *   当*数*为正无穷大时，返回正无穷大..
    *   结果是双倍。参数为零时的最小值。

    **示例:**

    ```
    Input: num = 25.18700000
    Output: 25.187000000000005

    ```

    下面的程序说明了 Java.lang.StrictMath.nextUp()方法:

    ```
    // Java praogram to illustrate the
    // Java.lang.StrictMath.nextUp() Method

    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double num1 = 67.1230000000;
            double num2 = 21.12, num3 = 0.0;

            // Returns floating-point value adjacent to num
            double nextUp_Value = StrictMath.nextUp(num1);
            System.out.println("The Next upper value is : "
                                           + nextUp_Value);

            double nextUp_Value1 = StrictMath.nextUp(num2);
            System.out.println("The Next upper value is : " 
                                          + nextUp_Value1);

            double nextUp_Value2 = StrictMath.nextUp(num3);
            System.out.println("The Next upper value is : " 
                                          + nextUp_Value2);
        }
    }
    ```

    **Output:**

    ```
    The Next upper value is : 67.12300000000002
    The Next upper value is : 21.120000000000005
    The Next upper value is : 4.9E-324

    ```

2.  The **nextUp(float num)** is the inbuilt method of StrictMath class in Java which is used to get the floating point value that is adjacent to *num* in the direction of positive infinity.Float.POSITIVE_INFINITY) but nextup() runs faster than its equivalent nextAfter call.

    **语法:**

    ```
    public static float nextUp(*float num*)
    ```

    **参数:**该方法接受一个浮点类型的参数*数*，该参数为起始浮点值。

    **返回值:**该方法返回接近正无穷大的相邻浮点值。它有三种特殊情况:

    *   当参数是 NaN 时，结果是 NaN。
    *   当*数*为正无穷大时，返回正无穷大..
    *   结果是“浮动”。参数为零时的最小值。

    **示例:**

    ```
    Input: num = 15.78f
    Output: 15.780000686645508

    ```

    下面的程序说明了 Java.lang.StrictMath.nextUp()方法:

    ```
    // Java praogram to illustrate the
    // Java.lang.StrictMath.nextUp() Method

    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            float num1 = 73.728f;
            float num2 = 51.71f, num3 = 0.0f;

            // Returns floating-point value adjacent to num
            double nextUp_Value = StrictMath.nextUp(num1);
            System.out.println("The Next upper value is : "
                                           + nextUp_Value);

            double nextUp_Value1 = StrictMath.nextUp(num2);
            System.out.println("The Next upper value is : "
                                          + nextUp_Value1);

            double nextUp_Value2 = StrictMath.nextUp(num3);
            System.out.println("The Next upper value is : "
                                          + nextUp_Value2);
        }
    }
    ```

    **Output:**

    ```
    The Next upper value is : 73.7280044555664
    The Next upper value is : 51.71000289916992
    The Next upper value is : 1.401298464324817E-45

    ```