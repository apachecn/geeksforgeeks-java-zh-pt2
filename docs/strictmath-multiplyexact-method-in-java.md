# Java 中的 StrictMath multiplyExact()方法

> 原文:[https://www . geesforgeks . org/strict math-multiplyxact-method-in-Java/](https://www.geeksforgeeks.org/strictmath-multiplyexact-method-in-java/)

1.  The **multiplyExact(*int num1, int num2*)** is an inbuilt function of StrictMath class in java which is used to get the product of the given arguments. When the result overflows an int i.e. Integer.MAX_VALUE then it throws an exception. Since this function is static so there is no need to create objects.
    **Syntax :**

    ```
    public static int multiplyExact(*int num1, int num2*)
    ```

    **参数:**该方法接受两个参数:

    *   *num1:* 这是代表一个参数的整数类型
    *   *num2:* 这是代表另一个参数的整数类型

    **返回值:**该方法返回 *num1* 和 *num2* 的乘积。
    **异常:**当结果溢出 int 时抛出*算术异常*。
    **示例:**

    ```
    Input: 
    num1 = 8
    nm2 = 7

    Output: 56

    ```

    下面的程序说明了 Java . lang . strict math . multiplyxact()方法。

    ```
    // Java praogram to illustrate the
    // Java.lang.StrictMath.multiplyExact()
    import java.lang.*;

    class Geeks {

        public static void main(String args[])
        {
            int num1 = 10, num2 = 5, num3 = -17, num4 = -2;
            System.out.println("Product of " + num1 + " and "
            + num2 + " is " + StrictMath.multiplyExact(num1, num2));

            System.out.println("Product of " + num3 + " and "
            + num4 + " is " + StrictMath.multiplyExact(num3, num4));

            System.out.println("Product of " + num2 + " and "
            + num4 + " is " + StrictMath.multiplyExact(num2, num4));
        }
    }
    ```

    **Output:**

    ```
    Product of 10 and 5 is 50
    Product of -17 and -2 is 34
    Product of 5 and -2 is -10

    ```

2.  The **multiplyExact(*long num1, int num2*)** is an inbuilt function of StrictMath class in java which is used to get the product of the given arguments. When the result overflows a long then it throws an exception. Since this function is static so there is no need to create objects.
    **Syntax :**

    ```
    public static long multiplyExact(*long num1, int num2*)
    ```

    **参数:**该方法接受一个两个参数:

    *   *num1:* 这是代表一个参数的长类型
    *   *num2:* 这是表示另一个参数的 int 类型

    **返回值:**该方法返回 *num1* 和 *num2* 的乘积。
    **异常:**当结果溢出一个 int 时抛出*算术异常*。
    **示例:**

    ```
    Input: 
    num1 = 8727
    nm2 = 2

    Output: 17454

    ```

    下面的程序说明了 Java . lang . strict math . multiplyxact()方法。

    ```
    // Java praogram to illustrate the
    // Java.lang.StrictMath.multiplyExact()
    import java.lang.*;

    class Geeks {

        public static void main(String args[])
        {
            long num1 = 2727810, num2 = 9892829;
            int num3 = 817, num4 = 3;
            System.out.println("Product of " + num1 + " and "
            + num2 + " is " + StrictMath.multiplyExact(num1, num2));

            System.out.println("Product of " + num3 + " and "
            + num4 + " is " + StrictMath.multiplyExact(num3, num4));

            System.out.println("Product of " + num2 + " and "
            + num4 + " is " + StrictMath.multiplyExact(num2, num4));
        }
    }
    ```

    **Output:**

    ```
    Product of 2727810 and 9892829 is 26985757874490
    Product of 817 and 3 is 2451
    Product of 9892829 and 3 is 29678487

    ```

3.  The **multiplyExact(*long num1, long num2*)** is an inbuilt function of StrictMath class in java which is used to get the product of the given arguments. When the result overflows a long then it throws an exception. Since this function is static so there is no need to create objects .
    **Syntax :**

    ```
    public static long multiplyExact(*long num1, long num2*)
    ```

    **参数:**该方法接受一个两个参数:

    *   *num1:* 这是代表一个参数的长类型
    *   *num2:* 这是代表另一个参数的长类型

    **返回值:**该方法返回 *num1* 和 *num2* 的乘积。
    **异常:**当结果溢出一长段时抛出*算术异常*。
    **示例:**

    ```
    Input: 
    num1 = 64954
    nm2 = 6643

    Output: 431489422

    ```

    下面的程序说明了 Java . lang . strict math . multiplyxact()方法。

    ```
    // Java praogram to illustrate the
    // Java.lang.StrictMath.multiplyExact()
    import java.lang.*;

    class Geeks {

        public static void main(String args[])
        {
            long num1 = 772810, num2 = 22929, num3 = -81827;
            long num4 = -823783;
            System.out.println("Product of " + num1 + " and "
            + num2 + " is " + StrictMath.multiplyExact(num1, num2));

            System.out.println("Product of " + num3 + " and "
            + num4 + " is " + StrictMath.multiplyExact(num3, num4));

            System.out.println("Product of " + num2 + " and "
            + num4 + " is " + StrictMath.multiplyExact(num2, num4));
        }
    }
    ```

    **Output:**

    ```
    Product of 772810 and 22929 is 17719760490
    Product of -81827 and -823783 is 67407691541
    Product of 22929 and -823783 is -18888520407

    ```