# Java 中可选的 orElseThrow()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-orelsthrow-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-orelsethrow-method-in-java-with-examples/)

**[的**or lsethrow()**方法。Java 中的](https://www.geeksforgeeks.org/java-util-package-java/)[可选类](https://www.geeksforgeeks.org/java-8-optional-class/)** 用于获取这个可选实例的值(如果存在的话)。如果此可选实例中没有值，则此方法将引发从指定供应商生成的异常。

**语法:**

```java
public <X> T
  orElseThrow(Supplier<X> exceptionSupplier)
  throws X extends Throwable

```

**参数:**此方法接受 **[供应商](https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/)** 作为类型 X 的参数，如果此可选实例中没有值，则抛出异常。

**返回供应商:**此方法返回此可选实例的**值**(如果存在)。如果此可选实例中没有值，则此方法将引发从指定供应商生成的异常。

**异常:**如果此可选实例中没有值，此方法将引发[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)。

下面的程序举例说明了 orElseThrow()方法:
**程序 1:**

```java
// Java program to demonstrate
// Optional.orElseThrow() method

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

        // orElseThrow supplier
        System.out.println(
            "Value by orElseThrow("
            + "ArithmeticException::new) method: "
            + op.orElseThrow(
                  ArithmeticException::new));
    }
}
```

**Output:**

```java
Optional: Optional[9455]
Value by orElseThrow(ArithmeticException::new) method: 9455

```

**程序 2:**

```java
// Java program to demonstrate
// Optional.orElseThrow() method

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

            // orElseThrow supplier
            System.out.println(
                "Value by orElseThrow("
                + "ArithmeticException::new) method: "
                + op.orElseThrow(
                      ArithmeticException::new));
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
java.lang.ArithmeticException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # orelstew-Java . util . function . supplier-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#orElseThrow-java.util.function.Supplier-)