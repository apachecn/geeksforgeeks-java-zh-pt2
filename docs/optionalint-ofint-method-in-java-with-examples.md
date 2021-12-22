# Java 中(Int)方法的选项列表，示例

> 原文:[https://www . geesforgeks . org/optional int-of int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-ofint-method-in-java-with-examples/)

(int) 方法的**帮助我们得到一个**选项**对象，它包含一个作为参数传递给这个方法的 int 值。**

**语法:**

```java
public static OptionalInt of(int value)

```

**参数:**该方法接受一个**整数值**作为参数，该参数将被设置为返回的选项线对象。

**返回值:**该方法返回一个存在值的**选项**。

以下程序说明了(int)方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalInt.of(int) method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // Create a OptionalInt instance
        // using of() method
        OptionalInt opInt
            = OptionalInt.of(452);

        // Get value of this OptionalInt instance
        System.out.println("OptionalInt: "
                           + opInt);
    }
}
```

**Output:**

```java
OptionalInt: OptionalInt[452]

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalInt.of(int) method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // Create a OptionalInt instance
        // using of() method
        OptionalInt opInt
            = OptionalInt.of(2149);

        // Get value of this OptionalInt instance
        System.out.println("OptionalInt: "
                           + opInt);
    }
}
```

**Output:**

```java
OptionalInt: OptionalInt[2149]

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # of(int)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#of(int))