# Java 中的 optionalduble or LSE(double)方法，示例

> 原文:[https://www . geesforgeks . org/optionaldouble-or else double-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-orelsedouble-method-in-java-with-examples/)

**orElse(double)** 方法帮助我们获取这个 OptionalDouble 对象中的值。如果一个值不在这个 OptionalDouble 中，那么这个方法返回作为参数传递的值。

**语法:**

```java
public double orElse(double other)

```

**参数:**如果没有值，该方法接受要返回的值的两倍。

**返回值:**该方法返回值，如果存在，否则为其他。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalDouble.orElse(double) method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opDouble = OptionalDouble.of(452146);

        // get value using orElse
        double value = opDouble.orElse(13421);

        // prdouble value
        System.out.println("value: " + value);
    }
}
```

**Output:**

```java
value: 452146.0

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalDouble.orElse(double) method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opDouble = OptionalDouble.empty();

        // get value using orElse
        double value = opDouble.orElse(13421);

        // prdouble value
        System.out.println("value: " + value);
    }
}
```

**Output:**

```java
value: 13421.0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # orElse(double)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#orElse(double))