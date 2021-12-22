# Java 中的 StrictMath max()方法示例

> 原文:[https://www . geesforgeks . org/strict math-max-method-in-Java-with-examples/](https://www.geeksforgeeks.org/strictmath-max-method-in-java-with-examples/)

java.lang.StrictMath.max()方法返回两个值中较大的一个**。该方法有四种变体，传递的参数类型不同。
所有这些都在下面讨论:**

1.  The **max(double num1, double num2)**is the inbuilt method which is used to get the maximum of two given double values arguments. It returns the same value when *num1* and *num2* have the same value. It returns NaN when either value is NaN, then the result is . It takes up negative zero to be strictly smaller than positive zero. It returns positive zero when one argument is positive zero and the other negative zero.

    **语法:**

    ```java
    public static double max(*double num1, double num2*)
    ```

    **参数:**该方法接受两个参数:

    *   代表参数的双类型的 *num1*
    *   代表另一个参数的双重类型的 num2

    **返回值:**该方法返回 *num1* 和 *num2* 中的较大值。

    **示例:**

    ```java
    Input: 
    num1 = 8
    nm2 = 19
    Output: 19.0

    ```

    下面的程序说明了 Java.lang.StrictMath.max()方法。
    **节目一:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.max()
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double num1 = 117, num2 = 711;

            double max_Value = StrictMath.max(num1, num2);
            System.out.println("max of the two num is " + max_Value);
        }
    }
    ```

    **Output:**

    ```java
    max of the two num is 711.0

    ```

    **程序 2:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.max()
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double num1 = -87, num2 = -11;

            double max_Value = StrictMath.max(num1, num2);
            System.out.println("max of the two num is " + max_Value);
        }
    }
    ```

    **Output:**

    ```java
    max of the two num is -11.0

    ```

    错误条件示例:

    ```java
    // Java praogram to illustrate the
    // error condition in
    // Java.lang.StrictMath.max() Method
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double num1 = 51, num2 = 71, num3 = 3, num4 = -93,
                   num5 = -93;
            double a = 0.0;

            num1 = a / 0.0;
            double max_Value = StrictMath.max(num1, a);
            System.out.println("max of the two num is " + max_Value);
        }
    }
    ```

    输出:

    ```java
    max of the two num is NaN

    ```

2.  The **max(float num1, float num2)** is the inbuilt method which is used to get the maximum of two given float values arguments. It returns the same value when *num1* and *num2* have the same value. It returns NaN when either value is NaN. It takes up negative zero to be strictly smaller than positive zero. It returns positive zero when one argument is positive zero and the other negative zero.

    **语法:**

    ```java
    public static float max(*float num1, float num2*)
    ```

    **参数:**该方法接受两个参数:

    *   *表示参数的浮点型 num1*
    *   *表示另一个参数的浮点型 num2*

    **返回值:**该方法返回 *num1* 和 *num2* 中的较大值。

    **示例:**

    ```java
    Input: 
    num1 = 87
    nm2 = 59
    Output: 87.0

    ```

    下面的程序说明了 Java.lang.StrictMath.max()方法。
    **节目一:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.max()
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            float num1 = 75, num2 = 81, num3 = -62, num4 = -62, num5 = -92;

            float max_Value = StrictMath.max(num1, num2);
            System.out.println("max of the two num is " + max_Value);

            float max_Value1 = StrictMath.max(num3, num4);
            System.out.println("max of the two num is " + max_Value1);

            float max_Value2 = StrictMath.max(num4, num5);
            System.out.println("max of the two num is " + max_Value2);
        }
    }
    ```

    **Output:**

    ```java
    max of the two num is 81.0
    max of the two num is -62.0
    max of the two num is -62.0

    ```

3.  The **max(int num1, int num2)**is the inbuilt method which is used to get the maximum of two given int values arguments. It returns the same value when *num1* and *num2* have the same value. It returns NaN when either value is NaN. It returns positive zero when one argument is positive zero and the other negative zero. In short, it returns the argument that is closer to the value of Integer.MAX_VALUE.
    **Syntax :**

    ```java
    public static int max(*int num1, int num2*)
    ```

    **参数:**该方法接受两个参数:

    *   表示参数的 int 类型的 num1
    *   表示另一个参数的 int 类型的 num2

    **返回值:**该方法返回 *num1* 和 *num2* 中的较大值。

    **示例:**

    ```java
    Input: 
    num1 = 13
    nm2 = 19
    Output: 19.0

    ```

    下面的程序说明了 Java.lang.StrictMath.max()方法。
    **节目一:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.max()
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            int num1 = 51, num2 = 72, num3 = -31, num4 = -31, num5 = -89;

            int max_Value = StrictMath.max(num1, num2);
            System.out.println("max of the two num is " + max_Value);

            int max_Value1 = StrictMath.max(num3, num4);
            System.out.println("max of the two num is " + max_Value1);

            int max_Value2 = StrictMath.max(num4, num5);
            System.out.println("max of the two num is " + max_Value2);
        }
    }
    ```

    **Output:**

    ```java
    max of the two num is 72
    max of the two num is -31
    max of the two num is -31

    ```

4.  The **max(long num1, long num2)** is the inbuilt method which is used to get the maximum of two given long values arguments. It returns the same value when *num1* and *num2* have the same value. It returns NaN when either value is NaN. In short it returns the argument that is closer to the value of Long.MAX_VALUE.
    **Syntax :**

    ```java
    public static long max(*long num1, long num2*)
    ```

    **参数:**该方法接受两个参数:

    *   代表参数的长型数值 1
    *   代表另一个参数的长类型的 num2

    **返回值:**该方法返回 *num1* 和 *num2* 中的较大值。

    **示例:**

    ```java
    Input: 
    num1 = 78772728
    nm2 =  1617177
    Output: 78772728.0

    ```

    下面的程序说明了 Java.lang.StrictMath.max()方法。
    **节目一:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.max()
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            long num1 = 87287, num2 = 787822, num3 = -3271, num4 = -3271,
                 num5 = -459;

            long max_Value = StrictMath.max(num1, num2);
            System.out.println("max of the two num is " + max_Value);

            long max_Value1 = StrictMath.max(num3, num4);
            System.out.println("max of the two num is " + max_Value1);

            long max_Value2 = StrictMath.max(num4, num5);
            System.out.println("max of the two num is " + max_Value2);
        }
    }
    ```

    **Output:**

    ```java
    max of the two num is 787822
    max of the two num is -3271
    max of the two num is -459

    ```