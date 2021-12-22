# Java 中可选的()方法，示例

> 原文:[https://www . geeksforgeeks . org/Java 可选方法示例/](https://www.geeksforgeeks.org/optional-of-method-in-java-with-examples/)

()的****的**法[的](https://www.geeksforgeeks.org/java-util-package-java/)法。Java 中的可选类**用于获取这个可选类的一个实例，该实例具有指定类型的指定值。

**语法:**

```java
public static <T> 
  Optional<T> of(T value)

```

**参数:**此方法接受**值**作为类型 T 的参数，以此值创建一个可选实例。

**返回值:**这个方法返回这个**可选类**的一个实例，带有指定类型的指定值。

**异常:**如果指定值为空，该方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

以下程序说明()方法:
**程序 1:**

```java
// Java program to demonstrate
// Optional.of() method

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
    }
}
```

**Output:**

```java
Optional: Optional[9455]

```

**程序 2:**

```java
// Java program to demonstrate
// Optional.of() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {
            // create a Optional
            Optional<Integer> op
                = Optional.of(null);

            // print value
            System.out.println("Optional: "
                               + op);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # of-T-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#of-T-)