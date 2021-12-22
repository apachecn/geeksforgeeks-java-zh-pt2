# Java 中的 OptionalDouble ifPresentOrElse()方法，带示例

> 原文:[https://www . geesforgeks . org/optionaldouble-if presentorelse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionaldouble-ifpresentorelse-method-in-java-with-examples/)

**if presentorelse([Java . util . function . DoubleConsumer](https://www.geeksforgeeks.org/doubleconsumer-interface-in-java-with-examples/)， [java.lang.Runnable](https://www.geeksforgeeks.org/runnable-interface-in-java/) )** 方法帮助我们执行指定的 double consumer 操作这个 OptionalDouble 对象的值。如果这个 OptionalDouble 中没有值，那么这个方法执行给定的基于空的 Runnable emptyAction，作为第二个参数传递

**语法:**

```java
public void ifPresentOrElse(DoubleConsumer action,
                            Runnable emptyAction)

```

**参数:**该方法接受两个参数:

*   **动作**:如果存在值，则在该可选项上执行的动作。
*   **空操作**:如果没有值，则执行空操作。

**返回值:**此方法不返回任何内容。

**异常:**如果存在一个值，并且给定的动作为空，或者不存在任何值，并且给定的基于空的动作为空，则该方法抛出**[null podoubleexception](https://www.geeksforgeeks.org/null-podoubleer-exception-in-java/)**。

下面的程序说明了 ifPresentOrElse()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalDouble.ifPresentOrElse() method

import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opdouble
            = OptionalDouble.of(234543.23453);

        // apply ifPresentOrElse
        opdouble.ifPresentOrElse(
            (value)
                -> { System.out.println(
                         "Value is present, its: "
                         + value); },
            ()
                -> { System.out.println(
                         "Value is empty"); });
    }
}
```

**输出:**

```java
Value is present, its: 12

```

**程序 2:**

```java
// Java program to demonstrate
// OptionalDouble.ifPresentOrElse method
import java.util.OptionalDouble;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalDouble
        OptionalDouble opdouble
            = OptionalDouble.empty();

        // apply ifPresentOrElse
        opdouble.ifPresentOrElse(
            (value)
                -> { System.out.println(
                         "Value is present, its: "
                         + value); },
            ()
                -> { System.out.println(
                         "Value is empty"); });
    }
}
```

**输出:**

```java
Value is empty

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optionaldouble . html # ifPresentOrElse(Java . util . function . double consumer，java.lang.Runnable)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalDouble.html#ifPresentOrElse(java.util.function.DoubleConsumer, java.lang.Runnable))