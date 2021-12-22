# 选项 Java 中的 orElseThrow(供应商)方法，示例

> 原文:[https://www . geesforgeks . org/optional int-or elsetowsupplier-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionalint-orelsethrowsupplier-method-in-java-with-examples/)

optionallint 类的 **orElseThrow(供应商)**方法，用于获取 optionallint 包含的值。如果存在值，此方法将返回该值，否则，此方法将引发异常提供函数产生的异常。例外供应商函数作为参数传递。

**语法:**

```java
public <X extends Throwable> int 
    orElseThrow(Supplier<?X> exceptionSupplier)
        throws X extends Throwable

```

**参数:**这个方法接受一个参数 exceptionSupplier，它是产生要抛出的异常的供应函数。

**返回值:**该方法返回值(如果存在)。

**异常:**该方法抛出以下异常:

*   x–如果不存在任何值。
*   NullPointerException–如果不存在任何值，并且异常提供函数为空
*   x 扩展了可投掷性

下面的程序说明了 orElseThrow(供应商)方法:
**程序 1:**

```java
// Java program to demonstrate
// OptionalInt.orElseThrow(Supplier) method
import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opint
            = OptionalInt.of(24);

        // apply orElseThrow(Supplier)
        int value
            = opint.orElseThrow(ArithmeticException::new);

        System.out.println("value " + value);
    }
}
```

**输出:**
![](img/16af1aed7536223ed92090c6389a998d.png)

**程序 2:**

```java
// Java program to demonstrate
// OptionalInt.orElseThrow(Supplier) method
import java.io.IOException;
import java.util.OptionalInt;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalInt
        OptionalInt opint
            = OptionalInt.empty();

        // apply orElseThrow(Supplier)
        int value;

        try {

            value
                = opint.orElseThrow(IOException::new);
        }
        catch (IOException e) {

            System.out.println("Exception " + e);
        }
    }
}
```

**输出:**
![](img/9a22b64b85356d897c5608696266bd89.png)

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional int . html # orelsthrow(Java . util . function . supplier)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalInt.html#orElseThrow(java.util.function.Supplier))