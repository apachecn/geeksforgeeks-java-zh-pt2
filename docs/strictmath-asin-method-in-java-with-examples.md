# Java 中的 StrictMath asin()方法，带示例

> 原文:[https://www . geesforgeks . org/strict math-asin-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/strictmath-asin-method-in-java-with-examples/)

**Java . lang . StrictMath . asin()**是 strict math 类的内置方法，用于返回指定值的反正弦。返回角度在*-π/2*和*π/2*范围内。该方法产生两个特殊结果:

*   如果参数的绝对值大于 1 或者参数本身是 NaN，那么结果也是 NaN。
*   如果传递的参数是 0，则输出也是 0，符号与参数相同。

**语法:**

```
public static double asin(*double val*)
```

**参数:**该方法接受一个双型参数*值*，指的是要返回其反正弦的值。

**返回值:**该方法返回自变量的反正弦值。
**例:**

```
Input: val = 0.72
Output: 0.80380231893303

Input: val = 7.0
Output: NAN

Input: val = 0.0
Output: 0.0

```

下面的程序说明了 java.lang.StrictMath.asin()方法:
**程序 1:**

```
// Java program to illustrate the
// java.lang.StrictMath.asin()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double val1 = 0.65, val2 = 3.00, val3 = 0;

        double asinvalue = StrictMath.asin(val1);
        System.out.println(" The arc sine value is = "+
                                            asinvalue);

        asinvalue = StrictMath.asin(val2);
        System.out.println("The arc sine value is = "+
                                            asinvalue);

        asinvalue = StrictMath.asin(val3);
        System.out.println("The arc sine value is = "+
                                           asinvalue);
    }
}
```

**Output:**

```
The arc sine value is = 0.7075844367253556
The arc sine value is = NaN
The arc sine value is = 0.0

```

**程序 2:**

```
// Java program to illustrate the
// java.lang.StrictMath.asin()
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        double val1 = -0.85, val2 = -2.00, val3 = 0;

        double asinvalue = StrictMath.asin(val1);
        System.out.println(" The arc sine value is = "+
                                            asinvalue);

        asinvalue = StrictMath.asin(val2);
        System.out.println("The arc sine value is = "+
                                            asinvalue);

        asinvalue = StrictMath.asin(val3);
        System.out.println("The arc sine value is= "+
                                            asinvalue);
    }
}
```

**Output:**

```
The arc sine value is = -1.015985293814825
The arc sine value is = NaN
The arc sine value is= 0.0

```