# Java 中的 StrictMath toIntExact()方法，带示例

> 原文:[https://www . geesforgeks . org/strict math-to textact-method-in-Java-with-examples/](https://www.geeksforgeeks.org/strictmath-tointexact-method-in-java-with-examples/)

**java . lang . strict math . toitexcact()**是 Java 中的一个内置方法，用于返回*长*参数的值。如果结果溢出一个 *int* 它将抛出一个异常。对象创建不是强制性的，因为 toIntExact(长数字)是静态的。

**语法:**

```java
public static int toIntExact(long num)
```

**参数:**该方法接受一个返回 int 值的*长*类型的参数**数**。

**返回值:**该方法将参数作为 int 返回。

**异常:**如果参数溢出一个 *int* 它会抛出**算术异常**。

**例:**

```java
Input: num = 2727l
Output: 2727

Input: num = -86262l
Output: -86262

```

下面的程序说明了 Java . lang . strict math . to textact()方法:

**程序 1:**

```java
// Java program to demonstrate working
// of java.lang.StrictMath.toIntExact() method

import java.lang.StrictMath;

class Geeks {

    // driver code
    public static void main(String args[])
    {

        // Get the long value
        // whose IntExact value is needed
        long num = 266526l;

        // Get the IntExact value
        // using toIntExact() method
        int intvalue = StrictMath.toIntExact(num);

        // Print the IntExact value
        System.out.print("IntExact value of "
                         + num + " = " + intvalue);
    }
}
```

**Output:**

```java
IntExact value of 266526 = 266526

```

**程序 2:**

```java
// Java program to demonstrate working
// of java.lang.StrictMath.toIntExact() method

import java.lang.StrictMath;

class Geeks {

    // driver code
    public static void main(String args[])
    {

        // Get the long value
        // whose IntExact value is needed
        long num = -7226526l;

        // Get the IntExact value
        // using toIntExact() method
        int intvalue = StrictMath.toIntExact(num);

        // Print the IntExact value
        System.out.print("IntExact value of "
                         + num + " = " + intvalue);
    }
}
```

**Output:**

```java
IntExact value of -7226526 = -7226526

```

**程序 3:** 演示算术异常

```java
// Java program to demonstrate working
// of java.lang.StrictMath.toIntExact() method

import java.lang.StrictMath;

class Geeks {

    // driver code
    public static void main(String args[])
    {

        try {
            // Get the long value
            // whose IntExact value is needed
            long num = 654456645546l;

            System.out.println("Trying to get "
                               + "IntExact value of: "
                               + num);

            // Get the IntExact value
            // using toIntExact() method
            int intvalue = StrictMath.toIntExact(num);

            // Print the IntExact value
            System.out.print("IntExact value of "
                             + num + " = " + intvalue);
        }
        catch (Exception e) {
            System.out.println("Exception throwm: " + e);
        }
    }
}
```

**Output:**

```java
Trying to get IntExact value of: 654456645546
Exception throwm: java.lang.ArithmeticException: integer overflow

```