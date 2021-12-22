# Java 中可选的 ifPresentOrElse()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-ifpresentorelse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-ifpresentorelse-method-in-java-with-examples/)

**[java.util](https://www.geeksforgeeks.org/java-util-package-java/) 的 **ifPresentOrElse(Consumer，Runnable)** 方法。[可选类](https://www.geeksforgeeks.org/java-8-optional-class/)** 帮助我们执行指定的消费者动作这个可选对象的值。如果该可选参数中没有值，则该方法执行给定的基于空的可运行空操作，作为第二个参数传递

**语法:**

```java
public void ifPresentOrElse(Consumer<T> action,
                            Runnable emptyAction)

```

**参数:**该方法接受两个参数:

*   **Action** : If there is a value, this is the action to be performed on this option.
*   **Empty action** : If there is no value, it is an empty action.

**返回值:**此方法不返回任何内容。

**异常:**如果存在一个值并且给定的操作为空，或者不存在值并且给定的基于空的操作为空，则该方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

下面的程序说明了 ifPresentOrElse()方法:

**注意:**由于这个方法是在 Java 9 中加入的，程序需要 JDK 9 来执行。

**节目 1:**

```java
// Java program to demonstrate
// Optional.ifPresentOrElse() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.of(9455);

        // print value
        System.out.println("Optional: "
                           + op);

        // apply ifPresentOrElse
        op.ifPresentOrElse(
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
Optional: Optional[9455]
Value is present, its: 9455

```

**节目 2:**

```java
// Java program to demonstrate
// Optional.ifPresentOrElse method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.empty();

        // print value
        System.out.println("Optional: "
                           + op);

        try {

            // apply ifPresentOrElse
            op.ifPresentOrElse(
                (value)
                    -> { System.out.println(
                             "Value is present, its: "
                             + value); },
                ()
                    -> { System.out.println(
                             "Value is empty"); });
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Optional: Optional.empty
Value is empty

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # ifPresentOrElse-Java . util . function . consumer-Java . lang . runnable-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#ifPresentOrElse-java.util.function.Consumer-java.lang.Runnable-)