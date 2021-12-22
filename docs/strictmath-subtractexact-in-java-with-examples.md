# Java 中的 StrictMath 减法精确()示例

> 原文:[https://www . geesforgeks . org/strict math-减法器-Java-in-examples/](https://www.geeksforgeeks.org/strictmath-subtractexact-in-java-with-examples/)

### 精确减法(int num1，int num2)

**减法精确(** ***int num1，int num2*** **)** 是 java 中 StrictMath 类的一个内置方法，用于得到给定参数 *num1* 和 *num2* 的差值。如果结果溢出 *int* ，则抛出异常。
由于减法精确( *int num1，int num2* )是静态的，因此对象创建不是强制性的。
**语法:**

```
public static int subtractExact(int num1, int num2)
```

**参数:**该方法接受两个参数:

*   **num1** :第一个整数值和
*   **num2** :从第一个中减去的第二个整数值。

**返回值:**该方法返回给定参数 *num1* 和 *num2* 的**差值**。
**异常:**如果结果溢出一个 *int* 它会抛出**算术异常**。
**示例:**

```
Input: num1 = 750, num2 = 50
Output: 700

Input: num1 = 361, num2 = 929
Output: -568
```

下面的程序说明了 java.lang.StrictMath .减法 Exact()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.subtractExact()

import java.lang.StrictMath;

class Geeks {

    // driver code
    public static void main(String args[])
    {

        // Get the int values
        // for which the difference is required
        int num1 = 76761;
        int num2 = 99;
        int num3 = 786616;

        // Get difference between
        // num1 and num2
        System.out.println("Difference of " + num1
                           + " and " + num2 + " = "
                           + StrictMath
                                 .subtractExact(num1, num2));

        // Get difference between
        // num1 and num3
        System.out.println("Difference of " + num1
                           + " and " + num3 + " = "
                           + StrictMath
                                 .subtractExact(num1, num3));
    }
}
```

**Output:** 

```
Difference of 76761 and 99 = 76662
Difference of 76761 and 786616 = -709855
```

### 减法精确(长 num1，长 num2)

**减法精确(** ***长 num1，长 num2*** **)** 是 java 中 StrictMath 类的一个内置方法，用于得到给定参数 *num1* 和 *num2* 的差值。如果结果溢出*长的*就会抛出异常。由于减法精确( *long num1，long num2* )是静态的，因此对象创建不是强制性的。
**语法:**

```
public static long subtractExact(long num1, long num2)
```

**参数:**该方法接受两个参数:

*   **num1** :第一个长值和
*   **num2** :从第一个长值中减去的第二个长值。

**返回值:**该方法返回给定参数 *num1* 和 *num2* 的**差值**。
**异常:**如果结果溢出一个*长的*，则抛出**算术异常**。
**示例:**

```
Input: num1 = 750, num2 = 50
Output: 700

Input: num1 = 361, num2 = 929
Output: -568
```

下面的程序说明了 java.lang.StrictMath .减法 Exact()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StrictMath.subtractExact()

import java.lang.StrictMath;

class Geeks {

    // driver code
    public static void main(String args[])
    {

        // Get the long values
        // for which the difference is required
        long num1 = -76342561;
        long num2 = 949;
        long num3 = 78326616;

        // Get difference between
        // num1 and num2
        System.out.println("Difference of " + num1
                           + " and " + num2 + " = "
                           + StrictMath
                                 .subtractExact(num1, num2));

        // Get difference between
        // num1 and num3
        System.out.println("Difference of " + num1
                           + " and " + num3 + " = "
                           + StrictMath
                                 .subtractExact(num1, num3));
    }
}
```

**Output:** 

```
Difference of -76342561 and 949 = -76343510
Difference of -76342561 and 78326616 = -154669177
```