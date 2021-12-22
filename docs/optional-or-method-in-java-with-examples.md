# Java 中可选的 or()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-or-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-or-method-in-java-with-examples/)

**或()**法的 **[法的](https://www.geeksforgeeks.org/java-util-package-java/)。如果存在任何值，Java 中的[可选类](https://www.geeksforgeeks.org/java-8-optional-class/)** 用于获取这个可选实例。如果此可选实例中没有值，则此方法返回一个可选实例，该实例具有从指定供应商生成的值。

**语法:**

```java
public Optional<T> or(Supplier<T> supplier)

```

**参数:**此方法接受 **[供应商](https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/)** 为 T 型参数，生成一个可选实例，其值由指定供应商生成。

**返回供应商:**此方法返回此**可选实例**，如果存在任何值。如果此可选实例中没有值，则此方法返回一个可选实例，该实例具有从指定供应商生成的值。

**异常:**如果提供函数为空或产生空结果，此方法将引发 NullPointerException。

以下程序说明或()方法:

**注意:**由于这个方法是在 Java 9 中加入的，程序需要 JDK 9 来执行。

**节目 1:**

```java
// Java program to demonstrate
// Optional.or() method

import java.util.*;
import java.util.function.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.of(9455);

        // print supplier
        System.out.println("Optional: "
                           + op);

        // or supplier
        System.out.println("Optional by or(() ->"
                           + " Optional.of(100)) method: "
                           + op.or(() -> Optional.of(100)));
    }
}
```

**输出:**

```java
Optional: Optional[9455]
Optional by or(() -> Optional.of(100)) method: Optional[9455]

```

**节目 2:**

```java
// Java program to demonstrate
// Optional.or() method

import java.util.*;
import java.util.function.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.empty();

        // print supplier
        System.out.println("Optional: "
                           + op);

        try {

            // or supplier
            System.out.println("Optional by or(() ->"
                               + " Optional.of(100)) method: "
                               + op.or(() -> Optional.of(100)));
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
Optional by or(() -> Optional.of(100)) method: Optional[100]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # or-Java . util . function . supplier-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#or-java.util.function.Supplier-)