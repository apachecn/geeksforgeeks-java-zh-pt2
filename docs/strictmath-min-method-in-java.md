# Java 中的 StrictMath min()方法，带示例

> 原文:[https://www . geesforgeks . org/strict math-min-method-in-Java/](https://www.geeksforgeeks.org/strictmath-min-method-in-java/)

java.lang.StrictMath.min()方法返回两个值中较小的一个**。该方法有四种变体，传递的参数类型不同。
所有这些都在下面讨论:**

1.  **min(double num1, double num2)** is the inbuilt method of StrictMath class which is used to get the least of given two **double** values arguments. It returns NaN when any of the arguments is NaN. It returns the same value when *num1* and *num2* have the same value. **min()** method assumes negative zero to be strictly smaller than positive zero.It returns negative zero when one argument is positive zero and the other is negative zero.
    **Syntax :**

    ```java
    public static double min(*double num1, double num2*)
    ```

    **参数:**该方法接受两个参数:

    *   代表一个参数的双类型的 *num1*
    *   代表另一个参数的双重类型的 num2

    **返回值:**该方法返回 *num1* 和 *num2* 中最小的一个。

    **示例:**

    ```java
    Input: 
    num1 = 9
    nm2 = 99
    Output: 9.0

    ```

    下面的程序说明了 Java.lang.StrictMath.min()方法。
    **节目一:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.min() Method
    // with double values passed
    // as parameters
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double num1 = 10, num2 = 40, num3 = -25, num4 = -25,
                   num5 = -17;

            double min_Value = StrictMath.min(num1, num2);
            System.out.println("min of the two num is " + min_Value);

            min_Value = StrictMath.min(num3, num4);
            System.out.println("min of the two num is " + min_Value);

            min_Value = StrictMath.min(num4, num5);
            System.out.println("min of the two num is " + min_Value);
        }
    }
    ```

    **Output:**

    ```java
    min of the two num is 10.0
    min of the two num is -25.0
    min of the two num is -25.0

    ```

    错误条件示例:

    ```java
    // Java praogram to illustrate the
    // error condition in
    // Java.lang.StrictMath.min() Method
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double num1 = 51, num2 = 71, num3 = 3, num4 = -93,
                   num5 = -93;
            double a = 0.0;

            num1 = a / 0.0;
            double min_Value = StrictMath.min(num1, a);
            System.out.println("min of the two num is " + min_Value);
        }
    }
    ```

    输出:

    ```java
    min of the two num is NaN

    ```

2.  The **min(float num1, float num2)** is the inbuilt method of StrictMath class which is used to get the least of given two float values arguments.It returns NaN when any of the arguments is NaN.It returns the same value when *num1* and *num2* have the same value. **min()** method assumes negative zero to be strictly smaller than positive zero.It returns negative zero when one argument is positive zero and the other is negative zero.
    **Syntax :**

    ```java
    public static float min(*float num1, float num2*)
    ```

    **参数:**该方法接受两个参数:

    *   *表示一个参数的浮点型 num1*
    *   *表示另一个参数的浮点型 num2*

    **返回值:**该方法返回 *num1* 和 *num2* 中最小的一个。

    **示例:**

    ```java
    Input: 
    num1 = 9
    nm2 = 5
    Output: 5.0

    ```

    下面的程序说明了 Java.lang.StrictMath.min()方法。
    **节目一:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.min() Method
    // with float values passed
    // as parameters
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            float num1 = 28, num2 = 82, num3 = -23, num4 = -23,
                  num5 = -11;

            float min_Value = StrictMath.min(num1, num2);
            System.out.println("min of the two num is " + min_Value);

            min_Value = StrictMath.min(num3, num4);
            System.out.println("min of the two num is " + min_Value);

            min_Value = StrictMath.min(num4, num5);
            System.out.println("min of the two num is " + min_Value);
        }
    }
    ```

    **Output:**

    ```java
    min of the two num is 28.0
    min of the two num is -23.0
    min of the two num is -23.0

    ```

3.  The **min(int num1, int num2)** is the inbuilt method of StrictMath class which is used to get the least of given two int values arguments.It returns NaN when any of the arguments is NaN.It returns the same value when *num1* and *num2* have the same value. **min()** method assumes negative zero to be strictly smaller than positive zero.Simply the argument closer to the value of Integer.MIN_VALUE is the result.
    **Syntax :**

    ```java
    public static int min(*int num1, int num2*)
    ```

    **参数:**该方法接受两个参数:

    *   *表示一个参数的 int 类型的 num1*
    *   表示另一个参数的 int 类型的 num2

    **返回值:**该方法返回 *num1* 和 *num2* 中最小的一个。

    **示例:**

    ```java
    Input: 
    num1 = 61
    nm2 = 18
    Output: 5.0

    ```

    下面的程序说明了 Java.lang.StrictMath.min()方法。
    **节目一:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.min() Method
    // with int values passed
    // as parameters
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            int num1 = 51, num2 = 71, num3 = -74, num4 = -93,
                num5 = -93;

            double min_Value = StrictMath.min(num1, num2);
            System.out.println("min of the two num is " + min_Value);

            min_Value = StrictMath.min(num3, num4);
            System.out.println("min of the two num is " + min_Value);

            min_Value = StrictMath.min(num4, num5);
            System.out.println("min of the two num is " + min_Value);
        }
    }
    ```

    **Output:**

    ```java
    min of the two num is 51.0
    min of the two num is -93.0
    min of the two num is -93.0

    ```

4.  The **min(long num1, long num2)** is the inbuilt method of StrictMath class which is used to get the least of given two long values arguments.It returns NaN when any of the arguments is NaN.It returns the same value when *num1* and *num2* have the same value. **min()** method assumes negative zero to be strictly smaller than positive zero.Simply the argument closer to the value of Long.MIN_VALUE is the result.
    **Syntax :**

    ```java
    public static long min(*long num1, long num2*)
    ```

    **参数:**该方法接受两个参数:

    *   代表一个参数的长类型的 num1
    *   代表另一个参数的长类型的 num2

    **返回值:**该方法返回 *num1* 和 *num2* 中最小的一个。

    **示例:**

    ```java
    Input: 
    num1 = 51617
    nm2 = 1345
    Output: 1345.0

    ```

    下面的程序说明了 Java.lang.StrictMath.min()方法。
    **节目一:**

    ```java
    // Java praogram to illustrate the
    // Java.lang.StrictMath.min() Method
    // with long values passed
    // as parameters
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            long num1 = 265626, num2 = 66671, num3 = -776264, num4 = -9263,
                 num5 = -97623;

            double min_Value = StrictMath.min(num1, num2);
            System.out.println("min of the two num is " + min_Value);

            min_Value = StrictMath.min(num3, num4);
            System.out.println("min of the two num is " + min_Value);

            min_Value = StrictMath.min(num4, num5);
            System.out.println("min of the two num is " + min_Value);
        }
    }
    ```

    **Output:**

    ```java
    min of the two num is 66671.0
    min of the two num is -776264.0
    min of the two num is -97623.0

    ```