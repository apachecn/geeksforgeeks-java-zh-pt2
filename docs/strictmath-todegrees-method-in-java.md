# Java 中的 StrictMath toDegrees()方法

> 原文:[https://www . geesforgeks . org/strict math-todegrees-method-in-Java/](https://www.geeksforgeeks.org/strictmath-todegrees-method-in-java/)

java 中 StrictMath 类的**Java . lang . strict math . todegrees()**方法用于接受以弧度度量的角度作为参数，并返回其以度数度量的近似等效角度。所以基本上它把弧度转换成度数。这种转换通常是不精确的。

**语法:**

```java
public static double toDegrees(*double rad*)
```

**参数:**该函数接受单个参数*弧度*，该参数是指以弧度为单位的角度，该角度将被转换为其等效度数。

**返回值:**该方法返回作为参数传递的角度的测量值，单位为度。

**例:**

```java
Input : 2.0
Output : 114.59155902616465

Input : 0.007022
Output : 0.4023309637408641

```

下面的程序说明了 java 中的**方法:**

**程序 1:**

```java
// Java Program to illustrate StrictMath.toDegrees()
// function 

import java.io.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        double rad = 3.0009871008;
        double deg = StrictMath.toDegrees(rad);
        System.out.println("Value in degrees of " +
                       rad + " radians is " + deg);
    }
}
```

**输出:**

```java
Value in degrees of 3.0009871008 radians is 171.943895249041

```

**程序二:**

```java
// Java Program to illustrate StrictMath.toDegrees()
//  function 

import java.io.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        double rad = 1.0;
        double deg = StrictMath.toDegrees(rad);
        System.out.println("Value in degrees of " +
                       rad + " radians is " + deg);
    }
}
```

**输出:**

```java
Value in degrees of 1.0 radians is 57.29577951308232

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/strict math . html # toDegrees()](https://docs.oracle.com/javase/8/docs/api/java/lang/StrictMath.html#toRadians())