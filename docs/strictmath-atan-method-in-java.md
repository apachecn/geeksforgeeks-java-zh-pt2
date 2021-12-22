# Java 中的 StrictMath atan()方法

> 原文:[https://www . geesforgeks . org/strict math-atan-method-in-Java/](https://www.geeksforgeeks.org/strictmath-atan-method-in-java/)

**Java . lang . StrictMath . atan()**是 strict math 类的内置方法，用于返回给定参数的正切值。返回角度在*-π/2*和*π/2*范围内。它产生了两个特殊的结果:

*   如果传递的参数是 NaN，则输出是 NaN。
*   如果传递的参数是 0，那么结果也是 0，保留与参数相同的符号。

**语法:**

```java
public static double atan(*double num*)
```

**参数:**该方法接受一个双精度类型的参数*数*，该参数是指正切值被返回的值。
**返回值:**该方法返回参数的反正切值。
**示例:**

```java
Input: num = 0.61
Output: 0.5477400137159024

Input: num = 0.0
Output: 0.0

Input: num = -71.0
Output: -1.5567127509720364
```

下面的程序说明了 java.lang.StrictMath.atan()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.atan()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 0.70, num2 = 55.00, num3 = 0;

        double atanValue = StrictMath.atan(num1);
        System.out.println("The arc tangent of " +
                         num1 + " = " + atanValue);

        atanValue = StrictMath.atan(num2);
        System.out.println("The arc tangent of " +
                         num2 + " = " + atanValue);

        atanValue = StrictMath.atan(num3);
        System.out.println("The arc tangent of " +
                          num3 + " = " + atanValue);
    }
}
```

**Output:** 

```java
The arc tangent of 0.7 = 0.6107259643892086
The arc tangent of 55.0 = 1.5526165117219184
The arc tangent of 0.0 = 0.0
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.atan()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = -0.52, num2 = -71.00, num3 = 0;

        double atanValue = StrictMath.atan(num1);
        System.out.println("The arc tangent of " +
                           num1 + " = " + atanValue);

        atanValue = StrictMath.atan(num2);
        System.out.println("The arc tangent of " +
                            num2 + " = " + atanValue);

        atanValue = StrictMath.atan(num3);
        System.out.println("The arc tangent of " +
                            num3 + " = " + atanValue);
    }
}
```

**Output:** 

```java
The arc tangent of -0.52 = -0.4795192919925962
The arc tangent of -71.0 = -1.5567127509720364
The arc tangent of 0.0 = 0.0
```