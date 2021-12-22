# Java 中的 OptionalDouble getAsDouble()方法，带示例

> 原文:[https://www . geesforgeks . org/optionaldouble-getasdouble-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-getasdouble-method-in-java-with-examples/)

**optionalduble**帮助我们创建一个可能包含也可能不包含双精度值的对象。 **getAsDouble()** 方法返回值如果 OptionalDouble 对象中有值，否则抛出**nosucheelementexception**。

**语法:**

```java
public double getAsDouble()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个 OptionalDouble 描述的值。

**异常:**如果不存在值，该方法抛出 **NoSuchElementException**

下面的程序说明了 getAsDouble()方法:

**程序 1:**

```java
// Java program to demonstrate
// OptionalDouble.getAsDouble() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // Create an OptionalDouble instance
        OptionalDouble opDouble
            = OptionalDouble.of(44356.455);

        System.out.println("OptionalDouble: "
                           + opDouble.toString());

        // Get value in this instance
        // using getAsDouble()
        System.out.println("Value in OptionalDouble = "
                           + opDouble.getAsDouble());
    }
}
```

**输出:**

```java
OptionalDouble: OptionalDouble[44356.455]
Value in OptionalDouble = 44356.455

```

**程序二:**

```java
// Java program to demonstrate
// OptionalDouble.getAsDouble() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        try {

            // Create an OptionalDouble instance
            OptionalDouble opDouble = OptionalDouble.empty();

            System.out.println("OptionalDouble: "
                               + opDouble.toString());

            // Get value in this instance
            // using getAsDouble()
            System.out.println("Value in OptionalDouble = "
                               + opDouble.getAsDouble());
        }
        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
OptionalDouble: OptionalDouble.empty
Exception: java.util.NoSuchElementException: No value present

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # getAsDouble()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#getAsDouble())