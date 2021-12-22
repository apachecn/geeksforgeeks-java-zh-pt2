# Java 中的 OptionalDouble orElseGet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/optionaldouble-or else get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-orelseget-method-in-java-with-examples/)

**or lseget([Java . util . function . double supplier](https://www.geeksforgeeks.org/java-8-doublesupplier-interface-with-examples/))**方法帮助我们获取这个 OptionalDouble 对象中的值。如果这个 OptionalDouble 中没有值，那么这个方法返回由提供函数产生的结果，作为参数传递

**语法:**

```
public double orElseGet(DoubleSupplier supplier)

```

**参数:**该方法接受产生返回值的供给函数。

**返回值:**该方法返回双精度值(如果存在)，否则返回提供函数产生的结果。

**异常:**如果没有值并且供应函数为空，该方法抛出**空值异常**。

下面的程序说明了 orElseGet([Java . util . function . double supplier](https://www.geeksforgeeks.org/java-8-doublesupplier-interface-with-examples/))方法:

**程序 1:**

```
// Java program to demonstrate
// OptionalDouble.orElseGet(DoubleSupplier) method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opdouble = OptionalDouble.of(2134);

        // get value using orElseGet
        double value = opdouble.orElseGet(() -> getdoubleValue());

        // prdouble value
        System.out.println("value: " + value);
    }

    public static double getdoubleValue()
    {
        return 3242 + 123;
    }
}
```

**输出:**

```
value: 2134.0

```

**程序二:**

```
// Java program to demonstrate
// OptionalDouble.orElseGet(DoubleSupplier) method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opdouble = OptionalDouble.empty();

        // get value using orElseGet
        double value = opdouble.orElseGet(() -> getdoubleValue());

        // prdouble value
        System.out.println("value: " + value);
    }

    public static double getdoubleValue()
    {
        return 3242 * 234;
    }
}
```

**输出:**

```
value: 758628.0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # orelsegget(Java . util . function . double supplier)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#orElseGet(java.util.function.DoubleSupplier))