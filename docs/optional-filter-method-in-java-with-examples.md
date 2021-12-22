# Java 中可选的 filter()方法，带示例

> 原文:[https://www . geesforgeks . org/optional-filter-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optional-filter-method-in-java-with-examples/)

**滤镜()**的**方法[爪哇](https://www.geeksforgeeks.org/java-util-package-java/)。Java 中的可选类**用于通过匹配给定的[谓词](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)来过滤这个可选实例的值，然后返回过滤后的可选实例。如果此可选实例中没有值，则此方法返回一个空的可选实例。

**语法:**

```java
public Optional<T> 
  filter(Predicale<T> predicate)

```

**参数:**该方法接受**谓词**作为类型谓词的参数，以此过滤可选实例。

**返回值:**该方法返回过滤后的可选实例。如果此可选实例中没有值，则此方法返回一个空的可选实例。

**异常:**如果指定的谓词为空，该方法抛出**空指针异常**。

下面的程序说明了 filter()方法:
**程序 1:**

```java
// Java program to demonstrate
// Optional.filter() method

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a Optional
        Optional<Integer> op
            = Optional.of(9456);

        // print value
        System.out.println("Optional: "
                           + op);

        // filter the value
        System.out.println("Filtered value "
                           + "for odd or even: "
                           + op
                                 .filter(num
                                         -> num % 2 == 0));
    }
}
```

**Output:**

```java
Optional: Optional[9456]
Filtered value for odd or even: Optional[9456]

```

**程序 2:**

```java
// Java program to demonstrate
// Optional.filter() method

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

            // filter the value
            System.out.println("Filtered value "
                               + "for odd or even: "
                               + op
                                     .filter(num
                                             -> num % 2 == 0));
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
Filtered value for odd or even: Optional.empty

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/optional . html # filter-Java . util . function . predicate-](https://docs.oracle.com/javase/9/docs/api/java/util/Optional.html#filter-java.util.function.Predicate-)