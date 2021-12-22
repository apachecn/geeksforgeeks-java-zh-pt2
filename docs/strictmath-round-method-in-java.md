# Java 中的 StrictMath round()方法

> 原文:[https://www . geesforgeks . org/strict math-round-method-in-Java/](https://www.geeksforgeeks.org/strictmath-round-method-in-java/)

### 圆形(双数字)

**轮(双 num)** 是 Java 中 [StrictMath 类的内置方法，用于获取给定参数 *num* 的最近长。它通过将 1/2 相加，取所得结果的底，然后将结果转换为 long 类型，将舍入值返回为整数。当参数为 NaN 且值等于 Long 的值时，它返回 0。当参数为负无穷大或小于或等于长值的任何值时，为 MIN_VALUE。最小值。此外，它还返回与 Long 值相等的值。当参数为正无穷大或大于或等于 Long 值的任何值时，为 MAX_VALUE。最大值。](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/)

**语法:**

```
public static long round(*double num*)
```

**参数:**该方法接受要取整的双型单参数*数*。

**返回值:**该方法将舍入值返回到作为参数传递给该方法的值的最近长值。

**示例:**

```
Input: num = 34.14
Output: 34

```

下面的程序说明了 round()方法:

**程序 1:**

```
// Java praogram to illustrate the
// java.lang.StrictMath.round()

import java.lang.*;

public class Geeks {
    public static void main(String[] args)
    {

        // Get a double number
        double num1 = 62.9;

        // Round off the double number using round() method
        long round_Value = StrictMath.round(num1);

        // Print the result
        System.out.println(" The round off value of "
                           + num1 + " = " + round_Value);

        // Get a double number
        double num2 = 87.1;

        // Round off the double number using round() method
        round_Value = StrictMath.round(num2);

        // Print the result
        System.out.println("The round off value of "
                           + num2 + " = " + round_Value);
    }
}
```

**Output:**

```
The round off value of 62.9 = 63
The round off value of 87.1 = 87

```

### 圆形(浮点数)

**轮(float num)** 是 Java 中 StrictMath 类的内置方法，我们使用它来获取与给定参数 *num* 最接近的 int。它通过将 1/2 相加，取所得结果的底，然后将结果转换为 int 类型，将舍入值返回为整数。当参数为 NaN 时，它返回 0，它返回的值等于整数的值。当参数为负无穷大或小于或等于整数值的任何值时，为最小值。最小值。它返回的值等于整数的值。当参数为正无穷大或大于或等于整数值的任何值时，为 MAX_VALUE。最大值。

**语法:**

```
public static int round(*float num*)
```

**参数:**该方法接受单参数*数*，为浮点型。

**返回值:**该方法返回舍入到最接近的 int 值的参数值。

**示例:**

```
Input: num = 72.15f
Output: 72

```

下面的程序说明了 java.lang.StrictMath.round()方法:

**程序 1:**

```
// Java praogram to illustrate the
// java.lang.StrictMath.round()

import java.lang.*;

public class Geeks {
    public static void main(String[] args)
    {

        // Get a float number
        float num1 = 87.1f;

        // Round off the float number using round() method
        int round_Value = StrictMath.round(num1);

        // Print the result
        System.out.println(" The round off value of "
                           + num1 + " = " + round_Value);

        // Get a float number
        float num2 = 92.9f;

        // Round off the float number using round() method
        round_Value = StrictMath.round(num2);

        // Print the result
        System.out.println("The round off value of "
                           + num2 + " = " + round_Value);
    }
}
```

**Output:**

```
The round off value of 87.1 = 87
The round off value of 92.9 = 93

```