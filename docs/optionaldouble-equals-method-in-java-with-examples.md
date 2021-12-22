# Java 中 OptionalDouble equals()方法，示例

> 原文:[https://www . geesforgeks . org/optionalduble-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-equals-method-in-java-with-examples/)

**optionalduble**帮助我们创建一个可能包含也可能不包含 Double 值的对象。 **equals(Object obj)** 方法帮助我们将这个 OptionalDouble 对象与作为参数传递的对象进行比较，如果对象相等，则返回 true。

另一个对象被认为等于这个 optionalduble，如果:

*   It is also an optionalduble, and;
*   The value or does not exist in both instances;
*   The present value is "equal" to each other through = =.

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受一个**对象**，它是一个待测对象是否相等。

**返回值:**如果另一个对象“等于”这个对象，这个方法返回真，否则返回假。

下面的程序说明了 equals(对象对象)方法:

**程序 1:**

```java
// Java program to demonstrate
// OptionalDouble.equals(Object obj) method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // Create first OptionalDouble object
        OptionalDouble opDouble1
            = OptionalDouble.of(452.13246);

        System.out.println("OptionalDouble 1: "
                           + opDouble1.toString());

        // Create second OptionalDouble object
        OptionalDouble opDouble2
            = OptionalDouble.of(452.13246);

        System.out.println("OptionalDouble 2: "
                           + opDouble2.toString());

        // Check if these two objects are equal
        // using equals(Object obj)
        System.out.println("Are both objects equal: "
                           + opDouble1.equals(opDouble2));
    }
}
```

**输出:**

```java
OptionalDouble 1: OptionalDouble[452.13246]
OptionalDouble 2: OptionalDouble[452.13246]
Are both objects equal: true

```

**程序二:**

```java
// Java program to demonstrate
// OptionalDouble.equals(Object obj) method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {
        // Create first OptionalDouble object
        OptionalDouble opDouble1
            = OptionalDouble.of(3179464.92);

        System.out.println("OptionalDouble 1: "
                           + opDouble1.toString());

        // Create second OptionalDouble object
        OptionalDouble opDouble2
            = OptionalDouble.of(4521.3246);

        System.out.println("OptionalDouble 2: "
                           + opDouble2.toString());

        // Check if these two objects are equal
        // using equals(Object obj)
        System.out.println("Are both objects equal: "
                           + opDouble1.equals(opDouble2));
    }
}
```

**输出:**

```java
OptionalDouble 1: OptionalDouble[3179464.92]
OptionalDouble 2: OptionalDouble[4521.3246]
Are both objects equal: false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # equals？(对象对象)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#equals(Object obj))