# Java 中的三角函数示例

> 原文:[https://www . geeksforgeeks . org/Java 三角函数示例/](https://www.geeksforgeeks.org/trigonometric-functions-in-java-with-examples/)

数学类包含执行基本数值运算的方法，如初等指数、对数、平方根和三角函数。

1.  **Java.lang.Math.sin() Method :** is an inbuilt method which returns the **sine** of the value passed as an argument. The value passed in this function should be in **radians**. If the argument is NaN or an infinity, then the result is NaN. If the argument is zero, then the result is a zero with the same sign as the argument.

    **语法:**

    ```java
    Math.sin(double radians)
    ```

    **参数:**
    该方法采用一个以弧度为单位的强制参数。

    **返回:**
    返回一个双精度值。返回值是传递的指定双精度值的正弦值。

    **示例 1 :** 演示 sin 用法的程序()

    ```java
    // Java program for sin() method
    import java.util.*;

    class GFG {

        // Driver Code
        public static void main(String args[])
        {

            double degrees = 45.0;

            // convert degrees to radians
            double radians = Math.toRadians(degrees);

            // sin() method to get the sine value
            double sinValue = Math.sin(radians);

            // prints the sine value
            System.out.println("sin(" + degrees + ") = " + sinValue);
        }
    }
    ```

    **输出:**

    ```java
    sin(45.0) = 0.7071067811865475

    ```

2.  **Java.lang.Math.cos() :** is an inbuilt method which returns the **cosine** of the value passed as an argument. The value passed in this function should be in **radians**. If the argument is NaN or an infinity, then the result is NaN.

    **语法:**

    ```java
    Math.cos(double radians)
    ```

    **参数:**
    该方法采用一个以弧度为单位的强制参数。

    **返回:**
    返回一个双精度值。返回值是传递的指定双精度值的余弦值。

    **示例 2 :** 演示 cos 使用的程序()

    ```java
    // Java program for cos() method
    import java.util.*;

    class GFG {

        // Driver Code
        public static void main(String args[])
        {

            double degrees = 45.0;

            // convert degrees to radians
            double radians = Math.toRadians(degrees);

            // cos() method to get the cosine value
            double cosValue = Math.cos(radians);

            // prints the cosine value
            System.out.println("cos(" + degrees + ") = " + cosValue);
        }
    }
    ```

    **输出:**

    ```java
    cos(45.0) = 0.7071067811865476

    ```

3.  **Java.lang.Math.tan() :** is an inbuilt method which returns the **tangent** of the value passed as an argument. The value passed in this function should be in **radians**. If the argument is NaN or an infinity, then the result is NaN. If the argument is zero, then the result is a zero with the same sign as the argument.
    **Syntax :**

    ```java
    Math.tan(double radians)
    ```

    **参数:**
    该方法采用一个以弧度为单位的强制参数。

    **返回:**
    返回一个双精度值。返回值是传递的指定双精度值的正切值。

    **示例 3 :** 演示 tan()使用的程序

    ```java
    // Java program for tan() method
    import java.util.*;

    class GFG {

        // Driver Code
        public static void main(String args[])
        {

            double degrees = 45.0;

            // convert degrees to radians
            double radians = Math.toRadians(degrees);

            // cos() method to get the tangent value
            double tanValue = Math.tan(radians);

            // prints the tangent value
            System.out.println("tan(" + degrees + ") = " + tanValue);
        }
    }
    ```

    **输出:**

    ```java
    tan(45.0) = 0.9999999999999999

    ```