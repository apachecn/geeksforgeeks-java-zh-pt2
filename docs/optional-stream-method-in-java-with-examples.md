# Java 中可选的 stream()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-stream-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-stream-method-in-java-with-examples/)

**流()**法 **[爪哇](https://www.geeksforgeeks.org/java-util-package-java/)。Java 中的可选类**用于获取这个可选实例中唯一值的顺序流。如果此可选实例中没有值，则此方法返回一个空流。

**语法:**

```
public Stream<T> stream()

```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回此可选实例中唯一值的顺序流。如果此可选实例中没有值，则此方法返回一个空流。

以下程序说明了 stream()方法:

**注意:**以下程序需要 JDK 9 及以上才能执行。

**节目 1:**

```
// Java program to demonstrate
// Optional.stream() method

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

        // get the Stream
        System.out.println("Getting the Stream:");
        op.stream().forEach(System.out::println);
    }
}
```

**输出:**

```
Optional: Optional[9455]
Getting the Stream:
9455

```

**节目 2:**

```
// Java program to demonstrate
// Optional.stream() method

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

            // get the Stream
            System.out.println("Getting the Stream:");
            op.stream().forEach(System.out::println);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Optional: Optional.empty
Getting the Stream:

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # stream–](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#stream--)