# Java 中可选的 orElseGet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/optional-or else get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-orelseget-method-in-java-with-examples/)

**[的**or lseget()**方法。Java 中的](https://www.geeksforgeeks.org/java-util-package-java/)[可选类](https://www.geeksforgeeks.org/java-8-optional-class/)** 用于获取这个可选实例的值(如果存在的话)。如果此可选实例中没有值，则此方法返回从指定供应商生成的值。

**语法:**

```
public T orElseGet(Supplier<T> supplier)

```

**参数:**此方法接受 **[供应商](https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/)** 作为类型 T 的参数，如果此可选实例中没有值，则生成一个要返回的值。

**返回供应商:**此方法返回此可选实例的**值**(如果存在)。如果此可选实例中没有值，则此方法返回从指定供应商生成的值。

**异常:**如果此可选实例中没有值，此方法将引发[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)。

以下程序举例说明 orElseGet()方法:
**程序 1:**

```
// Java program to demonstrate
// Optional.orElseGet() method

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

        // orElseGet supplier
        System.out.println("Value by orElseGet"
                           + "(Supplier) method: "
                           + op.orElseGet(
                                 () -> (int)(Math.random() * 10)));
    }
}
```

**Output:**

```
Optional: Optional[9455]
Value by orElseGet(Supplier) method: 9455

```

**程序 2:**

```
// Java program to demonstrate
// Optional.orElseGet() method

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

            // orElseGet supplier
            System.out.println("Value by orElseGet"
                               + "(Supplier) method: "
                               + op.orElseGet(
                                     () -> (int)(Math.random() * 10)));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Optional: Optional.empty
Value by orElseGet(Supplier) method: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # orElseGet-Java . util . function . supplier-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#orElseGet-java.util.function.Supplier-)