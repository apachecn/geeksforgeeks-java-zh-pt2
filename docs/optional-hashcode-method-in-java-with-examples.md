# Java 中可选的 hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-hashcode-method-in-java-with-examples/)

**[java.util](https://www.geeksforgeeks.org/java-util-package-java/) 的 hashCode()方法。Java 中的[可选类](https://www.geeksforgeeks.org/java-8-optional-class/)** 用来获取这个可选实例的 hashCode 值。如果此可选实例中没有值，则此方法返回 0。

**语法:**

```
public int hashCode()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个可选实例的**哈希值**。如果此可选实例中没有值，则此方法返回 0。

**异常:**这个方法不抛出任何异常。

**程序 1:**

```
// Java program to demonstrate
// the above method

import java.util.*;

public class OptionalDemo {
    public static void main(String[] args)
    {

        Optional<Integer> op
            = Optional.of(456);

        System.out.println("Optional: "
                           + op);

        System.out.println("Optional hashCode value: "
                           + op.hashCode());
    }
}
```

**输出:**

```
Optional: Optional[456]
Optional hashCode value: 456

```

**程序二:**

```
// Java program to demonstrate
// the above method

import java.util.*;

public class OptionalDemo {
    public static void main(String[] args)
    {

        Optional<Integer> op
            = Optional.empty();

        System.out.println("Optional: "
                           + op);

        System.out.println("Optional hashCode value: "
                           + op.hashCode());
    }
}
```

**输出:**

```
Optional: Optional.empty
Optional hashCode value: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#hashCode--)