# Java 中的 OptionalInt equals()方法，示例

> 原文:[https://www . geesforgeks . org/optional int-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-equals-method-in-java-with-examples/)

**选项链接**帮助我们创建一个可能包含也可能不包含整数值的对象。 **equals(Object obj)** 方法帮助我们将这个 OptionalInt 对象与作为参数传递的对象进行比较，如果对象相等，则返回 true。

另一个对象被认为等于这个选项线如果:

*   It is also an option line and;
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
// OptionalInt.equals(Object obj) method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // Create first OptionalInt object
        OptionalInt opInt1
            = OptionalInt.of(7258);

        System.out.println("OptionalInt 1: "
                           + opInt1.toString());

        // Create second OptionalInt object
        OptionalInt opInt2
            = OptionalInt.of(7258);

        System.out.println("OptionalInt 2: "
                           + opInt2.toString());

        // Check if these two objects are equal
        // using equals(Object obj)
        System.out.println("Are both objects equal: "
                           + opInt1.equals(opInt2));
    }
}
```

**输出:**

```java
OptionalInt 1: OptionalInt[7258]
OptionalInt 2: OptionalInt[7258]
Are both objects equal: true

```

**程序二:**

```java
// Java program to demonstrate
// OptionalInt.equals(Object obj) method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {
        // Create first OptionalInt object
        OptionalInt opInt1
            = OptionalInt.of(5422);

        System.out.println("OptionalInt 1: "
                           + opInt1.toString());

        // Create second OptionalInt object
        OptionalInt opInt2
            = OptionalInt.of(2737);

        System.out.println("OptionalInt 2: "
                           + opInt2.toString());

        // Check if these two objects are equal
        // using equals(Object obj)
        System.out.println("Are both objects equal: "
                           + opInt1.equals(opInt2));
    }
}
```

**输出:**

```java
OptionalInt 1: OptionalInt[5422]
OptionalInt 2: OptionalInt[2737]
Are both objects equal: false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionallint . html # equals？(对象对象)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#equals?(Object obj))