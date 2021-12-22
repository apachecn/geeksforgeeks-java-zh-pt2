# Java 中的 StrictMath exp()方法

> 原文:[https://www . geesforgeks . org/strict math-exp-method-in-Java/](https://www.geeksforgeeks.org/strictmath-exp-method-in-java/)

java.lang.StrictMath 类的所有方法:[集 1](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/) 、[集 2](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-2/)
**java . lang . strict math . exp()**是 Java 中的一个内置方法，用于返回一个欧拉数，该数的幂等于指定的双精度值。它产生了三个特殊的结果:

*   当给定的参数为正无穷大时，结果为正无穷大。
*   当参数为负无穷大时，结果为正零。
*   当给定的参数是 NaN 时，结果是 NaN。

**语法:**

```java
public static double exp(*double num*)
```

**参数:**该方法接受一个参数*数*，该参数为双型，是 e 要提升到的指数。
**返回值:**该方法返回值 *e^num* ，其中 e 是自然对数的基数。
**示例:**

```java
Input: num = 7
Output: 1096.6331584284585

Input: num = (1.0 / 0.0)
Output: Infinity
```

下面的程序说明了 java.lang.StrictMath.exp()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.exp()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = 0.0, num2 = (1.0 / 0.0);
        double num3 = 4;

        // Returns Euler's number e raised to the given power
        double expValue = StrictMath.exp(num1);
        System.out.println("The exp value of "+
                         num1+" = " + expValue);

        expValue = StrictMath.exp(num2);
        System.out.println("The exp value of "+
                         num2+" = " + expValue);

        expValue = StrictMath.exp(num3);
        System.out.println("The exp value of "+
                         num3+" = " + expValue);    }
}
```

**Output:** 

```java
The exp value of 0.0 = 1.0
The exp value of Infinity = Infinity
The exp value of 4.0 = 54.598150033144236
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StrictMath.exp()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double num1 = -0.0, num2 = (1.0 / 0.0);
        double num3 = 14;

        // Returns Euler's number e raised to the given power
        double expValue = StrictMath.exp(num1);
        System.out.println("The exp value of "+
                         num1+" = " + expValue);

        expValue = StrictMath.exp(num2);
        System.out.println("The exp value of "+
                         num2+" = " + expValue);

        expValue = StrictMath.exp(num3);
        System.out.println("The exp value of "+
                         num3+" = " + expValue);
    }
}
```

**Output:** 

```java
The exp value of -0.0 = 1.0
The exp value of Infinity = Infinity
The exp value of 14.0 = 1202604.2841647768
```