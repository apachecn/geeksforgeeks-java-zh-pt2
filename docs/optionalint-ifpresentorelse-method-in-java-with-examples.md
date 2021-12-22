# 选项 Java 中的 ifPresentOrElse()方法，带示例

> 原文:[https://www . geesforgeks . org/optional int-if presentorelse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-ifpresentorelse-method-in-java-with-examples/)

**if presentorelse([Java . util . function . IntConsumer](https://www.geeksforgeeks.org/intconsumer-interface-in-java-with-examples/)， [java.lang.Runnable](https://www.geeksforgeeks.org/runnable-interface-in-java/) )** 方法帮助我们执行指定的 IntConsumer 操作这个 OptionalInt 对象的值。如果该选项中没有值，则该方法执行给定的基于空的可运行空操作，作为第二个参数传递

**语法:**

```java
public void ifPresentOrElse(IntConsumer action,
                            Runnable emptyAction)

```

**参数:**该方法接受两个参数:

*   **动作**:如果存在值，则在该可选项上执行的动作。
*   **空操作**:如果没有值，则执行空操作。

**返回值:**此方法不返回任何内容。

**异常:**如果存在一个值并且给定的操作为空，或者不存在值并且给定的基于空的操作为空，则该方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

下面的程序说明了 ifPresentOrElse()方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalInt.ifPresentOrElse() method

import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opint = OptionalInt.of(12);

        // apply ifPresentOrElse
        opint.ifPresentOrElse(
            (value)
                -> { System.out.println("Value is present, its: "
                                        + value); },
            ()
                -> { System.out.println("Value is empty"); });
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
// OptionalInt.ifPresentOrElse method
import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opint = OptionalInt.empty();

        // apply ifPresentOrElse
        opint.ifPresentOrElse(
            (value)
                -> { System.out.println("Value is present, its: "
                                        + value); },
            ()
                -> { System.out.println("Value is empty"); });
    }
}
```

**输出:**

```java
Value is empty

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # ifPresentOrElse(Java . util . function . int consumer，java.lang.Runnable)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#ifPresentOrElse(java.util.function.IntConsumer, java.lang.Runnable))