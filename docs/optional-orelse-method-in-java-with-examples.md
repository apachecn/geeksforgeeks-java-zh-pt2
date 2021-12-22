# Java 中可选的 orElse()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-or else-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-orelse-method-in-java-with-examples/)

**的**or LSE()**法[爪哇](https://www.geeksforgeeks.org/java-util-package-java/)。Java 中的[可选类](https://www.geeksforgeeks.org/java-8-optional-class/)** 用于获取这个可选实例的值，如果存在的话。如果此可选实例中没有值，则此方法返回指定的值。

**语法:**

```java
public T orElse(T value)

```

**参数:**如果在这个可选实例中没有值，这个方法接受**值**作为类型 T 的参数返回。

**返回值:**该方法返回该可选实例的**值**(如果存在)。如果此可选实例中没有值，则此方法返回指定的值。

以下程序说明 orElse()方法:
**程序 1:**

```java
// Java program to demonstrate
// Optional.orElse() method

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

        // orElse value
        System.out.println("Value by orElse"
                           + "(100) method: "
                           + op.orElse(100));
    }
}
```

**Output:**

```java
Optional: Optional[9455]
Value by orElse(100) method: 9455

```

**程序 2:**

```java
// Java program to demonstrate
// Optional.orElse() method

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

            // orElse value
            System.out.println("Value by orElse"
                               + "(100) method: "
                               + op.orElse(100));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Optional: Optional.empty
Value by orElse(100) method: 100

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # orElse-T-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#orElse-T-)