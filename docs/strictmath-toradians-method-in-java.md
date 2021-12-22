# Java 中的 StrictMath toRadians()方法

> 原文:[https://www . geesforgeks . org/strict math-tora dians-method-in-Java/](https://www.geeksforgeeks.org/strictmath-toradians-method-in-java/)

Java 中 [StrictMath 类的**Java . lang . strict math . toradians()**方法用于接受以度数测量的角度作为参数，并返回以弧度测量的近似等效角度。所以基本上它把度数转换成弧度。这种转换通常是不精确的。](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/)

**语法:**

```
public static double toRadians(*double deg*)
```

**参数:**该函数接受单个参数*度*，该参数指的是要转换为其等效弧度的角度。

**返回值:**该方法返回作为参数传递的角度的测量值，单位为弧度。

**示例:**

```
Input : 120
Output : 2.0943951023931953

Input : 0.00087104
Output : 1.5202515916571408E-5

```

下面的程序说明了 java 中的**方法:
**程序 1:****

```
// Java Program to illustrate 
// StrictMath.toRadians() function 

import java.io.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        double deg = 108.478;
        double rad = StrictMath.toRadians(deg);
        System.out.println("Value in radian of " +
                      deg + " degrees is " + rad);
    }
}
```

**Output:**

```
Value in radian of 108.478 degrees is 1.8932982659784086

```

**程序 2:**

```
// Java Program to illustrate StrictMath.toRadians()
// function 

import java.io.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {

        double deg = 360.0;
        double rad = StrictMath.toRadians(deg);
        System.out.println("Value in radian of " +
                      deg + " degrees is " + rad);
    }
}
```

**Output:**

```
Value in radian of 360.0 degrees is 6.283185307179586

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/strict math . html # toRadians()](https://docs.oracle.com/javase/8/docs/api/java/lang/StrictMath.html#toRadians())