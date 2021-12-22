# Java 中的 StrictMath atan2()方法

> 原文:[https://www . geesforgeks . org/strict math-atan 2-method-in-Java/](https://www.geeksforgeeks.org/strictmath-atan2-method-in-java/)

**java . lang . strict math . atan2()**是 Java 中的一个内置方法，用于计算在 *-pi* 和 *pi* 之间范围内的纵坐标 _val/横坐标 _ val 的反正切。返回直角坐标*(横坐标 _val，纵坐标 _val)* 到极坐标 *(p，角度)*的转换角度。

*   当*横坐标 _val* 为负零且*纵坐标 _val* 为负时，或*横坐标 _val* 为负有限且*纵坐标 _val* 为负无穷大时，结果为最接近-pi 的二倍值。
*   当两个参数都为正无穷大时，结果是最接近 pi/4 的双精度值。
*   当任一参数为 NaN 时，结果为 NaN。
*   当*横坐标 _val* 为正零点且*纵坐标 _val* 为正时，或者*横坐标 _val* 为正有限且*纵坐标 _val* 为正无穷大时，结果为正零点。
*   当*横坐标 _val* 为负零且*纵坐标 _val* 为正时，或者*横坐标 _val* 为负有限且*纵坐标 _val* 为正无穷大时，结果为负零。
*   当*横坐标 _val* 为正零而*纵坐标 _val* 为负时，或者*横坐标 _val* 为正有限且*纵坐标 _val* 为负无穷大时，结果为最接近 pi 的二倍值。
*   当*横坐标 _val* 为正且*纵坐标 _val* 为正零或负零，或者*横坐标 _val* 为正无穷大且*纵坐标 _val* 为有限时，结果为最接近π/2 的二倍值。
*   当*横坐标 _val* 为负且*纵坐标 _val* 为正零或负零，或者*横坐标 _val* 为负无穷大且*纵坐标 _val* 为有限时，结果为最接近-pi/2 的二倍值。
*   当两个参数都为正无穷大时，结果是最接近 pi/4 的双精度值。
*   当*横坐标 _val* 为正无穷大而*纵坐标 _val* 为负无穷大时，结果是最接近 3*pi/4 的二倍值。
*   当*横坐标 _val* 为负无穷大而*纵坐标 _val* 为正无穷大时，结果是最接近-pi/4 的二倍值。
*   当两个参数都为负无穷大时，结果是最接近-3*pi/4 的双精度值。

**语法:**

```
public static double atan2(*double abscissa_val, double ordinate_val* )
```

**参数:**该方法接受两个参数:

*   *纵坐标 _val:* 这是作为纵坐标的双重类型。
*   *横坐标 _val:* 这是双型，为横坐标。

**返回值:**该方法返回该点(横坐标 _val，纵坐标 _val)对应的极坐标中点(p，角度)的θ分量。
下面的程序说明了 java.lang.StrictMath.atan2()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.atan2()

import java.lang.*;

public class Geeks{

public static void main(String[] args) {

    double abs_val = 0.3 , ord_val = 50.00;

    // It returns the theta component
    // in polar coordinates
    double atan2val = StrictMath.atan2(abs_val,
                                          ord_val);
    System.out.println("Arc tangent value is: "
                                        +atan2val);

}
}
```

**Output:** 

```
Arc tangent value is: 0.00599992800155516
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.atan2()

import java.lang.*;

public class Geeks{

public static void main(String[] args) {

    double abs_val = 0.3 , ord_val = -50.00;

    // It returns the theta component
    // in polar coordinates

    double atan2val = StrictMath.atan2(abs_val,
                                          ord_val);
    System.out.println("Arc tangent value is: "
                                        +atan2val);

}
}
```

**Output:** 

```
Arc tangent value is: 3.135592725588238
```

**程序 3:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.atan2()

import java.lang.*;

public class Geeks{

public static void main(String[] args) {

    double abs_val = -0.3 ,ord_val = 50.00;

    // It returns the theta component
    // in polar coordinates

    double atan2val = StrictMath.atan2(abs_val,
                                          ord_val);
    System.out.println("Arc tangent value is: "
                                        +atan2val);

}
}
```

**Output:** 

```
Arc tangent value is: -0.00599992800155516
```

**程序 4:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.atan2()

import java.lang.*;

public class Geeks{

public static void main(String[] args) {

    double abs_val = -0.3 , ord_val = -50.00;

    // It returns the theta component
    // in polar coordinates

    double atan2val = StrictMath.atan2(abs_val,
                                          ord_val);
    System.out.println("Arc tangent value is: "
                                        +atan2val);

}
}
```

**Output:** 

```
Arc tangent value is: -3.135592725588238
```