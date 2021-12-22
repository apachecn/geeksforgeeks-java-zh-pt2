# Java 中可选的 get()方法，示例

> 原文:[https://www . geesforgeks . org/optional-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-get-method-in-java-with-examples/)

**得到()**法的**T3。Java 中的可选类**用来获取这个可选实例的值。如果此可选实例中没有值，则此方法将引发空指针异常。

**语法:**

```
public T get()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回可选类这个实例的**值**。

**异常:**如果这个可选实例中没有值，这个方法抛出**nosuchelementexception**。

下面的程序说明 get()方法:
**程序 1:**

```
// Java program to demonstrate
// Optional.get() method

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

        // get the value
        System.out.println("Value of this Optional: "
                           + op.get());
    }
}
```

**Output:**

```
Optional: Optional[9455]
Value of this Optional: 9455

```

**程序 2:**

```
// Java program to demonstrate
// Optional.get() method

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

            // get the value
            System.out.println("Value of "
                               + "this Optional: "
                               + op.get());
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
java.util.NoSuchElementException: No value present

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # get–](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#get--)