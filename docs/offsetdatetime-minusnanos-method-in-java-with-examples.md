# Java 中的 offset datetime MINUS()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-mins nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-minusnanos-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的**亚纳米()**方法返回这个 OffsetDateTime 的一个副本，从解析的日期和时间中减去指定的纳米秒数。

**语法:**

```java
public OffsetDateTime minusNanos(long nano-seconds)

```

**参数:**该方法接受单个参数**纳米秒**，该参数指定要从解析的日期中减去的纳米秒。它也可以是负的，在这种情况下，它会加上纳秒数。

**返回值:**根据该日期时间返回偏移日期时间，减去纳米秒，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了*亚纳米()*方法:

**程序 1:**

```java
// Java program to demonstrate the minusNanos() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse("2018-12-12T13:30:30+05:00");

        // Prints dates
        System.out.println("Date1: " + date1);

        // Subtracts the number of nano-seconds
        System.out.println("Date1 after subtracting nano-seconds: "
                           + date1.minusNanos(-120));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting nano-seconds: 2018-12-12T13:30:30.000000120+05:00

```

**程序二** :

```java
// Java program to demonstrate the minusNanos() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse("2018-12-12T13:30:30+05:00");

        // Prints dates
        System.out.println("Date1: " + date1);

        // Subtracts the number of nano-seconds
        System.out.println("Date1 after subtracting nano-seconds: "
                           + date1.minusNanos(140));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting nano-seconds: 2018-12-12T13:30:29.999999860+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # minusonas(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#minusNanos(long))