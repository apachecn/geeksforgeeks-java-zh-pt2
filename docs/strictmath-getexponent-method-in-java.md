# Java 中的 strict math getindex()方法

> 原文:[https://www . geesforgeks . org/strict math-get index-method-in-Java/](https://www.geeksforgeeks.org/strictmath-getexponent-method-in-java/)

1.  The **getExponent(double num)** is an inbuilt method of StrictMath class which is used to get the unbiased exponent to be used in the representation of a given double argument. It gives rise to two special results:
    *   结果将是*翻倍。当给定参数为 NaN 或无穷大时，MAX _ INDEX+1*
    *   结果是*翻倍。当参数为零时，最小指数–1*。

    **语法:**

    ```
    public static int getExponent(*double num*)
    ```

    **参数:**该方法接受一个双类型的参数*数*，其无偏指数应该被找到。

    **返回值:**该方法返回在给定双参数的表示中使用的无偏指数。

    **示例:**

    ```
    Input: num = 75.45
    Output: 6.0

    Input: num = 0.0
    Output: -1023.0

    ```

    下面的程序举例说明了 Java . lang . strict math . getindex()方法:

    ```
    // Java praogram to illustrate the
    // java.lang.StrictMath.getExponent()
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            double value = 93.5;

            /* Here it returns the unbiased exponent which  
               is used in the representation of a double*/
            double exp_Value = StrictMath.getExponent(value);
            System.out.print("Exponent of " + value + " = ");
            System.out.println(exp_Value);
        }
    }
    ```

    **Output:**

    ```
    Exponent of 93.5 = 6.0

    ```

2.  The **getExponent(*float num*)** is an inbuilt method of StrictMath class which is used to get an unbiased exponent, to be used in the representation of a given float argument. It gives rise to two special results:
    *   结果将是*浮动。当给定参数为 NaN 或无穷大时，MAX _ INDEX+1*
    *   结果是*浮动。当参数为零时，最小指数–1*。

    **语法:**

    ```
    public static int getExponent(*float num*)
    ```

    **参数:**这个方法接受一个参数*数*，这个参数是浮点型的，我们要找到它的无偏指数。

    **返回值:**该方法返回在给定浮点参数的表示中使用的无偏指数。

    **示例:**

    ```
    Input: num = 10254.25f
    Output: 13.0

    Input: num = 10.25f
    Output: 3.0

    ```

    下面的程序举例说明了 Java . lang . strict math . getindex()方法:

    ```
    // Java praogram to illustrate the
    // java.lang.StrictMath.getExponent()
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            float value = 10254.25f;

            /* Here it returns the unbiased exponent which 
               is used in the representation of a float*/
            double exp_Value = StrictMath.getExponent(value);
            System.out.print("Exponent of " + value + " = ");
            System.out.println(exp_Value);
        }
    }
    ```

    **Output:**

    ```
    Exponent of 10254.25 = 13.0

    ```