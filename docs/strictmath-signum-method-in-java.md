# Java 中的 StrictMath signum()方法

> 原文:[https://www . geesforgeks . org/strict math-signum-method-in-Java/](https://www.geeksforgeeks.org/strictmath-signum-method-in-java/)

1.  The **signum(*double num*)** is an inbuilt method of StrictMath class in Java which is used to get the signum method of the argument which means:
    *   如果参数为零，则结果为零。
    *   当参数大于零时，结果为 1.0。
    *   如果参数小于零，则结果为-1.0。

    **语法:**

    ```java
    public static double signum(*double num*)
    ```

    **参数:**该方法接受一个双类型的单参数*数*，代表要返回其符号的参数。
    **返回值:**该方法返回参数 *num* 的 signum 函数。它还会产生两种不同的结果:

    *   当第一个参数是 NaN 时，结果是 NaN。
    *   结果与 *num* 为正零或负零时的参数 *num* 相同。

    **示例:**

    ```java
    Input: num = 72.88d
    Output: 1.0

    Input: num = -72.88d
    Output: -1.0

    Input: num = 0.0d
    Output: 0.0

    ```

    下面的程序说明了 Java . lang . strict math . signum(double)方法的工作原理。

    ```java
    // Java praogram to illustrate the
    // java.lang.StrictMath.signum(double)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double num1 = 46.82d, num2 = 0.0d, num3 = -0.0d, num4 = -18.2d;

            // It returns 1.0 since the argument is greater than zero
            double sig_val = StrictMath.signum(num1);
            System.out.println("Signum Value = " + sig_val);

            sig_val = StrictMath.signum(num2);
            System.out.println("Signum Value = " + sig_val);

            sig_val = StrictMath.signum(num3);
            System.out.println("Signum Value = " + sig_val);

            sig_val = StrictMath.signum(num4);
            System.out.println("Signum Value = " + sig_val);
        }
    }
    ```

    **Output:**

    ```java
    Signum Value = 1.0
    Signum Value = 0.0
    Signum Value = -0.0
    Signum Value = -1.0

    ```

2.  The **signum(*float num*)** is an inbuilt method of StrictMath class in Java which is used to get the signum method of the argument which means:
    *   如果参数为零，则结果为零。
    *   当参数大于零时，结果为 1.0。
    *   如果参数小于零，则结果为-1.0。

    **语法:**

    ```java
    public static float signum(*float num*)
    ```

    **参数:**该方法接受一个浮点类型的单个参数*数*，表示要返回其符号的参数。

    **返回值:**该方法返回参数*数*的 signum 函数。它还会产生两种不同的结果:

    *   当第一个参数是 NaN 时，结果是 NaN。
    *   结果与 *num* 为正零或负零时的参数 *num* 相同。

    **示例:**

    ```java
    Input: num = 11.8f
    Output: 1.0

    Input: num = -55.88f
    Output: -1.0

    Input: num = 0.0f
    Output: 0.0

    ```

    下面的程序说明了 Java . lang . strict math . signum(float)方法的工作原理:

    ```java
    // Java praogram to illustrate the
    // java.lang.StrictMath.signum(float)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            float num1 = 7.22f, num2 = 0.0f, num3 = -0.0f, num4 = -18.11f;

            // It returns 1.0 since the argument is greater than zero
            float sig_val = StrictMath.signum(num1);
            System.out.println("Signum Value = " + sig_val);

            sig_val = StrictMath.signum(num2);
            System.out.println("Signum Value = " + sig_val);

            sig_val = StrictMath.signum(num3);
            System.out.println("Signum Value = " + sig_val);

            sig_val = StrictMath.signum(num4);
            System.out.println("Signum Value = " + sig_val);
        }
    }
    ```

    **Output:**

    ```java
    Signum Value = 1.0
    Signum Value = 0.0
    Signum Value = -0.0
    Signum Value = -1.0

    ```