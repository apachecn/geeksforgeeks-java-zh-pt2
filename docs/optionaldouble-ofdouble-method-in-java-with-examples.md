# Java 中(Double)方法的 OptionalDouble 示例

> 原文:[https://www . geesforgeks . org/optionalduble-of double-in-Java-method-with-examples/](https://www.geeksforgeeks.org/optionaldouble-ofdouble-method-in-java-with-examples/)

(double) 方法的**帮助我们获得一个**optionalduble**对象，该对象包含一个作为参数传递给该方法的双精度值。**

**语法:**

```
public static OptionalDouble of(double value)

```

**参数:**该方法接受一个**双精度值**作为参数，该参数将被设置为返回的 OptionalDouble 对象。

**返回值:**该方法返回一个具有当前值的**选项子包**。

以下程序说明了(双)法:
**程序 1:**

```
// Java program to demonstrate
// OptionalDouble.of(double) method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // Create a OptionalDouble instance
        // using of() method
        OptionalDouble opDouble
            = OptionalDouble.of(45213.246);

        // Get value of this OptionalDouble instance
        System.out.println("OptionalDouble: "
                           + opDouble);
    }
}
```

**Output:**

```
OptionalDouble: OptionalDouble[45213.246]

```

**程序 2:**

```
// Java program to demonstrate
// OptionalDouble.of(double) method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // Create a OptionalDouble instance
        // using of() method
        OptionalDouble opDouble
            = OptionalDouble.of(21438999);

        // Get value of this OptionalDouble instance
        System.out.println("OptionalDouble: "
                           + opDouble);
    }
}
```

**Output:**

```
OptionalDouble: OptionalDouble[2.1438999E7]

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # of(double)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#of(double))