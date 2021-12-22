# Java 中的 OptionalDouble 空()方法，带示例

> 原文:[https://www . geesforgeks . org/optionalduble-空-java 中的方法-示例/](https://www.geeksforgeeks.org/optionaldouble-empty-method-in-java-with-examples/)

**optionalduble**帮助我们创建一个可能包含也可能不包含 Double 值的对象。 **empty()** 方法返回一个空的 OptionalDouble 实例。此选项没有值。所以我们可以说这个方法帮助我们创建了一个空的 OptionalDouble 对象。

**语法:**

```java
public static OptionalDouble empty()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个空的 OptionalDouble。

下面程序举例说明空()方法:

**程序 1:**

```java
// Java program to demonstrate
// OptionalDouble.empty() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        // using empty method
        OptionalDouble opDouble
            = OptionalDouble.empty();

        // Print the created instance
        System.out.println("OptionalDouble: "
                           + opDouble.toString());
    }
}
```

**输出:**

```java
OptionalDouble: OptionalDouble.empty

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # empty()](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#empty())