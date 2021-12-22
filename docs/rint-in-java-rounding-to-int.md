# Java 中的 rint()(四舍五入为 int)

> 原文:[https://www.geeksforgeeks.org/rint-in-java-rounding-to-int/](https://www.geeksforgeeks.org/rint-in-java-rounding-to-int/)

rint()是 Java 中的一个内置方法，用于将浮点参数舍入为整数值(浮点格式)。

**语法:**

```java
Math.rint(double n)
```

**参数:**
rint()函数取一个强制的单参数值进行舍入。

**返回:**
返回一个双精度值。此方法返回与参数值最接近的整数。

**代码#1:** 演示 rint()函数使用的程序

```java
// Java program for implementation of
// rint() method
import java.util.*;
class GFG {

    // Driver Code
    public static void main(String args[])
    {
        double x = 12.6;
        double y = 12.2;

        // rint() method use to return the 
        // closest value to the argument
        double rintx = Math.rint(x);
        double rinty = Math.rint(y);

        // Prints the rounded numbers
        System.out.println(rintx);
        System.out.println(rinty);
    }
}
```

**输出:**

```java
13.0
12.0

```

**异常:**
如果小数点后有 0.5，将四舍五入到最接近的偶数双精度值。

**代码#2:** 解释异常的程序

```java
// Java program for implementation of
// rint() method exception
import java.util.*;
class GFG {

    // Driver Code
    public static void main(String args[])
    {
        double x = 1.5;
        double y = 2.5;

        // rounds upto 2 which is the nearest
        // even double value
        double rintx = Math.rint(x);
        double rinty = Math.rint(y);

        System.out.println(rintx);
        System.out.println(rinty);
    }
}
```

**输出:**

```java
2.0
2.0

```