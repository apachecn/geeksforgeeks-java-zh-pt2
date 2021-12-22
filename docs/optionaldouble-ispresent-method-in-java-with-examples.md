# optionalduble 是 Java 中的 Present()方法，带有示例

> 原文:[https://www . geesforgeks . org/optionaldouble-is present-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-ispresent-method-in-java-with-examples/)

**optionalduble**帮助我们创建一个可能包含也可能不包含 Double 值的对象。 **isPresent()** 方法帮助我们得到了在 OptionalDouble 对象中是否存在双精度值的答案。如果存在双精度值，则返回 true，否则返回 false。

**语法:**

```java
public boolean isPresent()

```

**参数:**此方法不接受任何内容。

**返回值:**如果存在值，则该方法返回真，否则返回假

下面的程序说明了 isPresent()方法:

**程序 1:**

```java
// Java program to demonstrate
// OptionalDouble.isPresent() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opDouble
            = OptionalDouble.of(3148.1345);

        // get value using isPresent()
        System.out.println("OptionalDouble"
                           + " has a value= "
                           + opDouble.isPresent());
    }
}
```

**输出:**

```java
OptionalDouble has a value= true

```

**程序二:**

```java
// Java program to demonstrate
// OptionalDouble.isPresent() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opDouble
            = OptionalDouble.empty();

        // try to get that value is present or not
        boolean response = opDouble.isPresent();

        if (response)
            System.out.println("Value present");
        else
            System.out.println("Value absent");
    }
}
```

**输出:**

```java
Value absent

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # isPresent()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#isPresent())