# Java 中的 StrictMath nextAfter()方法

> 原文:[https://www . geesforgeks . org/strict math-next after-method-in-Java/](https://www.geeksforgeeks.org/strictmath-nextafter-method-in-java/)

1.  The **nextAfter(*double start, double direction*)** is the inbuilt method of StrictMath class in Java which is used to get the float number, adjacent to the *start* in the direction of the second argument *direction*. This method gives rise to few conditions depending on the type and variation of parameters.
    *   当两个参数相等时，结果是第二个参数。
    *   当任何一个参数是 NaN 时，结果就是 NaN。
    *   当两个参数都是有符号的 0 时，结果是*方向*没有任何变化。
    *   当*开始*是*双倍时，结果是零，符号与*开始*相同。最小值*和*方向*的值使得结果具有较小的幅度。
    *   结果是*翻倍。MAX_VALUE* 符号与*相同当*开始*为无穷大且*方向*有一个值使得结果应该有一个较小的量值时开始*。
    *   当*开始*等于*加倍时，结果是一个符号相同的*开始*的无穷大。最大值*和*方向*的值应使结果具有更大的幅度。

    **语法:**

    ```
    public static double nextAfter(*double start, double direction*)
    ```

    **参数:**该方法接受两个参数:

    *   *start:* 这是指起始浮点值的双精度类型。
    *   *方向:*这是双类型，指的是指示应该返回 start 的邻居还是 start 的值。

    **返回值:**该方法向*方向*重新运行与*开始*相邻的浮点数。

    **示例:**

    ```
    Input: start = 72.74d
           direction = 1.2d

    Output: 72.73999999999998

    ```

    下面的程序说明了 java.lang.StrictMath.nextAfter()方法:

    ```
    // Java program to demonstrate nextAfter()

    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double start = 23.62d, direction = 0.0d;

            double result = StrictMath.nextAfter(start, direction);
            System.out.println("The NextAfter is = " + result);

            result = StrictMath.nextAfter(start, 9.2d);
            System.out.println("The NextAfter is = " + result);

            result = StrictMath.nextAfter(direction, 7.2d);
            System.out.println("The NextAfter is =" + result);

            // Returns 0 if both arguments are zero
            result = StrictMath.nextAfter(direction, 0.0d);
            System.out.println("The NextAfter is =" + result);
        }
    }
    ```

    **Output:**

    ```
    The NextAfter is = 23.619999999999997
    The NextAfter is = 23.619999999999997
    The NextAfter is =4.9E-324
    The NextAfter is =0.0

    ```

2.  The **nextAfter(*float start, double direction*)** is an inbuilt method of StrictMath class in Java which is used to get the float number which is adjacent to the *start* in the direction of the second argument *direction* .
    *   当两个参数相等时，结果是第二个参数。
    *   当任何一个参数是 NaN 时，结果就是 NaN。
    *   当两个参数都是有符号的 0 时，结果是*方向*没有任何变化。
    *   当*开始*为浮动时，结果是零，符号与*开始*相同。最小值和*方向*的值应使结果具有较小的幅度。
    *   结果是浮动。当*开始*是无限的并且*方向*有一个值使得结果应该有一个较小的幅度时，与*开始*符号相同的 MAX_VALUE。
    *   当*开始*等于浮动时，结果是一个无穷大，符号与*开始*相同。最大值和*方向*的值应使结果具有更大的幅度。

    **语法:**

    ```
    public static double nextAfter(*float start, double direction*)
    ```

    **参数:**该方法接受两个参数:

    *   *start:* 这是浮点类型，指的是起始浮点值。
    *   *方向:*这是双类型，指的是指示应该返回 start 的邻居还是 start 的值。

    **返回值:**该方法重新运行浮点数，邻近*开始*方向的*方向*方向。

    **示例:**

    ```
    Input: start = 22.2f
           direction = 0.0d

    Output: 22.20000076293945

    ```

    下面的程序说明了 java.lang.StrictMath.nextAfter()方法:

    ```
    // Java program to demonstrate nextAfter()

    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double start = 42.9f;
            double direction = 0.0d;

            double result = StrictMath.nextAfter(start, direction);
            System.out.println("The NextAfter is = " + result);

            result = StrictMath.nextAfter(start, 9.2d);
            System.out.println("The NextAfter is = " + result);

            result = StrictMath.nextAfter(direction, 7.2d);
            System.out.println("The NextAfter is =" + result);

            // Returns 0 if both arguments is zero
            result = StrictMath.nextAfter(direction, 0.0d);
            System.out.println("The NextAfter is =" + result);
        }
    }
    ```

    **Output:**

    ```
    The NextAfter is = 42.9000015258789
    The NextAfter is = 42.9000015258789
    The NextAfter is =4.9E-324
    The NextAfter is =0.0

    ```