# Java 中的 StrictMath copySign()

> 原文:[https://www.geeksforgeeks.org/strictmath-copysign-in-java/](https://www.geeksforgeeks.org/strictmath-copysign-in-java/)

1.  The **copySign(*float mvalue, float sign*)** is an inbuilt method of StrictMath class in Java which is used to get the first floating-point argument with the sign of the second floating-point argument. A NaN sign argument in this function is considered as a positive.
    **Syntax :**

    ```
    public static float copySign(*float mvalue, float sign*)
    ```

    **参数:**该方法接受两个参数:

    *   *值:*这是浮点类型，提供结果的大小。
    *   *符号:*这是提供结果符号的浮点类型。

    **返回值:**该方法返回一个带大小和符号的值。

    **示例:**

    ```
    Input: 
    mvalue = 5
    sign = -1

    Output = -5.0

    ```

    下面的程序说明了 Java . lang . strict math . copy sign(*float mv value，float sign* )方法:

    ```
    // Java praogram to illustrate the
    // java.lang.StrictMath.copySign(float mvalue, float sign)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            float a1 = 7;
            float a2 = -1;
            float a3 = 1;

            float svalue = StrictMath.copySign(a1, a2);
            System.out.println("The value of a1 with sign a2: "
                                                     + svalue);

        svalue = StrictMath.copySign(a1, a3); 
        System.out.println("The value of a1 with sign a3: "
                                                     + svalue);
        }
    }
    ```

2.  The **copySign(*double magnitude, double sign*)** is an inbuilt method of StrictMath class in Java which is used to get the first double argument with the sign of the second double argument. A NaN sign argument in this function is considered as a positive.
    **Syntax :**

    ```
    public static double copySign(*double mvalue, double sign*)
    ```

    **参数:**该方法接受两个参数:

    *   *值:*这是提供结果大小的双精度类型。
    *   *符号:*这是提供结果符号的双重类型。

    **返回值:**该方法返回一个带大小和符号的值。
    **例:**

    ```
    Input: 
    mvalue = 6.9
    sign = -1

    Output = -6.9

    ```

    下面程序举例说明了 Java . lang . strict math . copy sign(*双量级，双符号*)方法:

    ```
    // Java praogram to illustrate the
    // java.lang.StrictMath.copySign(double magnitude, double sign)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double a1 = 4.7, a2 = -1, a3 = 1, a4 = -62;

            /* Returns the first double argument with the 
             sign of the second double argument */
            double svalue = StrictMath.copySign(a1, a2);
            System.out.println("The value of a1 with sign a2 :" 
                                                      + svalue);

            svalue = StrictMath.copySign(a1, a3);
            System.out.println("The value of a1 with sign a3 :" 
                                                      + svalue);

            svalue = StrictMath.copySign(a2, a4);
            System.out.println("The value of a2 with sign a4 :" 
                                                      + svalue);
        }
    }
    ```