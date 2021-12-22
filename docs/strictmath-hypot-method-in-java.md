# Java 中的 StrictMath hypot()方法

> 原文:[https://www . geesforgeks . org/strict math-hypt-method-in-Java/](https://www.geeksforgeeks.org/strictmath-hypot-method-in-java/)

根据基本几何学，*斜边*只不过是直角三角形的最长边。它是与三角形的直角相对的一边。为了求直角三角形斜边的长度，应用了毕达哥拉斯定理。根据这个定理，给定长度为 p 和 b 的三角形的两条垂直边，斜边可以由公式![$\sqrt{x^2+y^2}$  ](img/5ce07df94ea2130141db54f952dfed69.png "Rendered by QuickLaTeX.com")求出。
The**Java . lang . StrictMath . hypot()**是 strict math 类的一种内置方法，用于获取给定两边或自变量的平方和的斜边或平方根，即![$\sqrt{num1^2+num2^2}$  ](img/9c8d454cb7b322e601f23aab6e238077.png "Rendered by QuickLaTeX.com")。该方法排除了所有中间上溢和下溢。它很少产生特殊的结果:

*   当 *num1* 或 *num2* 为无穷大时，该方法返回正无穷大。
*   当任何一个参数都是 NAN 并且两个参数都不是无穷大时，它返回 NAN。

**语法:**

```java
public static double hypot(*double num1, double num2*)
```

**参数:**该方法接受两个 Double 类型的参数:

*   *num1:* 这是任意一边的第一个值。
*   *num2:* 这是另一边的第二个值。

**返回值:**该方法返回![$\sqrt{num1^2+num2^2}$  ](img/9c8d454cb7b322e601f23aab6e238077.png "Rendered by QuickLaTeX.com")，即斜边长度。
**示例:**

```java
Input: num1 = 3
       num2 = 4

Output: 5.0
```

下面的程序说明了 Java.lang.StrictMath.hypot()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// Java.lang.StrictMath.hypot() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 11, num2 = 13.8;

        // It returns the hypotenuse
        double hypotlen = StrictMath.hypot(num1, num2);
        System.out.println("Length of hypotenuse  of side "
        + num1 + " & " + num2 + " = " + hypotlen);
    }
}
```

**Output:** 

```java
Length of hypotenuse  of side 11.0 & 13.8 = 17.647662734764623
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// Java.lang.StrictMath.hypot() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = -54, num2 = -24.8;

        // It returns the hypotenuse
        double hypotlen = StrictMath.hypot(num1, num2);
        System.out.println("Length of hypotenuse  of side "
        + num1 + " & " + num2 + " = " + hypotlen);
    }
}
```

**Output:** 

```java
Length of hypotenuse  of side -54.0 & -24.8 = 59.422554640473
```

**程序 3:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// Java.lang.StrictMath.hypot() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 4;
        double positive_Infinity = Double.POSITIVE_INFINITY;
        double negative_Infinity = Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;

        // When 1 or more argument is NAN
        double hypotlen = StrictMath.hypot(nan, num1);
        System.out.println("Hypotenuse length = " + hypotlen);

        // When both arguments are infinity
        hypotlen = StrictMath.hypot(positive_Infinity,
                                    negative_Infinity);
        System.out.println("Hypotenuse length = " + hypotlen);
    }
}
```

**Output:** 

```java
Hypotenuse length = NaN
Hypotenuse length = Infinity
```