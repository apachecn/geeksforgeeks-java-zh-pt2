# Java 中可选的 equals()方法，示例

> 原文:[https://www . geesforgeks . org/optional-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-equals-method-in-java-with-examples/)

**T1 的 equals()方法。Java 中的[可选类](https://www.geeksforgeeks.org/java-8-optional-class/)** 用于检查该可选与指定可选是否相等。此方法获取一个可选实例，并将其与该可选实例进行比较，然后返回一个表示该实例的布尔值。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受一个参数**对象**，该参数是要检查是否与该可选参数相等的可选参数。

**返回值:**这个方法返回一个**布尔**，告诉这个可选值是否等于指定的对象。

**异常:**这个方法不抛出任何异常。

**程序 1:**

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class OptionalDemo {
    public static void main(String[] args)
    {

        Optional<Integer> op1
            = Optional.of(456);

        System.out.println("Optional 1: "
                           + op1);

        Optional<Integer> op2
            = Optional.of(456);

        System.out.println("Optional 2: "
                           + op2);

        System.out.println("Comparing Optional 1"
                           + " and Optional 2: "
                           + op1.equals(op2));
    }
}
```

**输出:**

```java
Optional 1: Optional[456]
Optional 2: Optional[456]
Comparing Optional 1 and Optional 2: true

```

**程序二:**

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class OptionalDemo {
    public static void main(String[] args)
    {

        Optional<Integer> op1
            = Optional.of(456);

        System.out.println("Optional 1: "
                           + op1);

        Optional<Integer> op2
            = Optional.empty();

        System.out.println("Optional 2: "
                           + op2);

        System.out.println("Comparing Optional 1"
                           + " and Optional 2: "
                           + op1.equals(op2));
    }
}
```

**输出:**

```java
Optional 1: Optional[456]
Optional 2: Optional.empty
Comparing Optional 1 and Optional 2: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#equals-java.lang.Object-)