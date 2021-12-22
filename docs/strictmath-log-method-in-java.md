# Java 中的 StrictMath log()方法

> 原文:[https://www . geesforgeks . org/strict math-log-method-in-Java/](https://www.geeksforgeeks.org/strictmath-log-method-in-java/)

**Java . lang . StrictMath . log()**是 strict math 类的内置方法，用于计算给定双精度值的自然对数，即以 e 为底的对数。它产生了三个特殊的结果:

*   当参数为正无穷大时，它返回正无穷大。
*   当参数为 NaN 或小于零时，它返回 NaN。
*   当参数为正零或负零时，结果为负无穷大。

**语法:**

```
public static double log(*double num*)
```

**参数:**该方法接受一个双类型的参数*数*，其对数值将被找到。
**返回值:**该方法返回 *num* 的自然对数的值。
**示例:**

```
Input: num = 5.0 
Output: 1.6094379124341003

Input: num = 10.0 
Output:  2.302585092994046
```

下面的程序说明了 Java.lang.StrictMath.log()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// Java.lang.StrictMath.log() Method
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double num1 = 10 , num2 = 25.2 ;

    // It returns natural logarithm(base e)
    double log_Value = StrictMath.log(num1);
    System.out.print("Log value of " + num1 + " = " );
    System.out.println(log_Value);

    log_Value = StrictMath.log(num2);
    System.out.print("Log value of " + num2 + " = " );
    System.out.println(log_Value);

}
}
```

**Output:** 

```
Log value of 10.0 = 2.302585092994046
Log value of 25.2 = 3.2268439945173775
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// Java.lang.StrictMath.log() Method
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double num1 = 0 , num2 = (1.0/0.0) , num3 = 1;

    // It returns natural logarithm(base e)
    double log_Value = StrictMath.log(num1);
    System.out.print("Log value of " + num1 + " = " );
    System.out.println(log_Value);

    log_Value = StrictMath.log(num2);
    System.out.print("Log value of " + num2 + " = " );
    System.out.println(log_Value);

    log_Value = StrictMath.log(num3);
    System.out.print("Log value of " + num3 + " = " );
    System.out.println(log_Value);

}
}
```

**Output:** 

```
Log value of 0.0 = -Infinity
Log value of Infinity = Infinity
Log value of 1.0 = 0.0
```