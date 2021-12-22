# Java 中可选的 ofNullable()方法，示例

> 原文:[https://www . geesforgeks . org/optional-of nullable-in-Java-method-with-examples/](https://www.geeksforgeeks.org/optional-ofnullable-method-in-java-with-examples/)

**的**法。Java 中的可选类**用于获取这个可选类的一个实例，该实例具有指定类型的指定值。如果指定的值为空，则此方法返回可选类的空实例。**

**语法:**

```java
public static <T>
  Optional<T> ofNullable(T value)

```

**参数:**此方法接受**值**作为类型 T 的参数，以此值创建可选实例。它可以为空。

**返回值:**这个方法用指定类型的指定值返回这个可选类的一个**实例**。如果指定的值为空，则此方法返回可选类的空实例。

以下程序举例说明了 ofNullable()方法:
**程序 1:**

```java
// Java program to demonstrate
// Optional.ofNullable() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op1
            = Optional.ofNullable(9455);

        // print value
        System.out.println("Optional 1: "
                           + op1);
    }
}
```

**Output:**

```java
Optional 1: Optional[9455]

```

**程序 2:**

```java
// Java program to demonstrate
// Optional.ofNullable() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // create a Optional
        Optional<String> op2
            = Optional.ofNullable(null);

        // print value
        System.out.println("Optional 2: "
                           + op2);
    }
}
```

**Output:**

```java
Optional 2: Optional.empty

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # of nullable-T-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#ofNullable-T-)