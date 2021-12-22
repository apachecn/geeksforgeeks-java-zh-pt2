# Java 中的 toDegrees()和 toRadians()

> 原文:[https://www.geeksforgeeks.org/todegrees-toradians-java/](https://www.geeksforgeeks.org/todegrees-toradians-java/)

**toDegrees()** 是 java 中的一个内置方法，它将参数值转换为[度](https://en.wikipedia.org/wiki/Degree_symbol)。

**语法:**

```
 Math.toDegrees(double d)
```

**参数:**
参数是强制的，并且必须是双数据类型。传递的参数因此被转换为度数。

**返回**
返回一个数据类型的值。传递的参数被转换为度数并被返回。

**代码#1** :解释 toDegrees()实现的程序

```
// Java program for implementation of
// toDegrees() method
import java.util.*;
class GFG {

    // Driver Code
    public static void main(String args[])
    {
        double x = 12.0;
        double y = 19.0;

        // conversion of number to degrees using
        // inbuilt function
        double xinDegrees = Math.toDegrees(x);
        double yinDegrees = Math.toDegrees(y);

        // Prints the number in degrees
        System.out.println(xinDegrees);
        System.out.println(yinDegrees);
    }
}
```

**Output:**

```
687.5493541569879
1088.619810748564

```

**输出:**

```
687.5493541569879
1088.619810748564

```

**toRadians()** 是 java 中的一个内置方法，可以将参数值转换为[弧度](https://en.wikipedia.org/wiki/Radian)。

**语法:**

```
 Math.toRadians(double d)
```

**参数:**
参数是强制的，并且必须是双数据类型。传递的参数因此被转换为弧度。

**返回**
返回一个数据类型的值。传递的参数被转换为弧度并被返回。

**代码#2:** 解释 toRadians()实现的程序

```
// Java program for implementation of
// toRadians() method
import java.util.*;
class GFG {

    // Driver Code
    public static void main(String args[])
    {
        double x = 12.0;
        double y = 19.0;

        // conversion of number to Radians using
        // inbuilt function
        double xinRadians = Math.toRadians(x);
        double yinRadians = Math.toRadians(y);

        // Prints the number in Radians
        System.out.println(xinRadians);
        System.out.println(yinRadians);
    }
}
```

**Output:**

```
0.20943951023931953
0.33161255787892263

```