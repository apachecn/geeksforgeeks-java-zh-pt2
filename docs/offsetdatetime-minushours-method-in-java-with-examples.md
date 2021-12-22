# Java 中的 OffsetDateTime minusHours()方法，带示例

> 原文:[https://www . geesforgeks . org/offset datetime-minoshours-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-minushours-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的**minush()**方法返回这个 OffsetDateTime 的一个副本，从解析的日期和时间中减去指定的小时数。

**语法:**

```
public OffsetDateTime minusHours(long hours)

```

**参数:**该方法接受单个参数**小时数**，该参数指定要从解析的日期中减去的小时数。它也可以是负数，在这种情况下，它会加上小时数。

**返回值:**根据该日期时间返回一个偏移日期时间，减去小时，不为空。

**异常:**当超出支持的数据和时间范围时，程序抛出**日期时间异常**。

以下程序说明了*稳定小时()*方法:

**程序 1:**

```
// Java program to demonstrate the minusHours() method

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

        // Subtracts the number of hours
        System.out.println("Date1 after subtracting hours: "
                           + date1.minusHours(-120));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting hours: 2018-12-17T13:30:30+05:00

```

**程序二** :

```
// Java program to demonstrate the isEqual() method

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

        // Subtracts the number of hours
        System.out.println("Date1 after subtracting hours: "
                           + date1.minusHours(140));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting hours: 2018-12-06T17:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # minoshours(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#minusHours(long))