# Java 中的 OffsetDateTime minusMonths()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-MINUS months-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-minusmonths-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **minusMonths()** 方法返回这个 OffsetDateTime 的一个副本，从解析的日期和时间中减去指定的月数。

**语法:**

```
public OffsetDateTime minusMonths(long months)
```

**参数:**该方法接受单个参数**月份**，该参数指定要从解析的日期中减去的月份。它也可以是负数，在这种情况下，它会加上月数。

**返回值:**根据这个日期时间返回一个 OffsetDateTime，减去月份，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了*次月()*方法:

**程序 1:**

```
// Java program to demonstrate the minusMonths() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse(
                      "2018-12-12T13:30:30+05:00");

        // Prints dates
        System.out.println("Date1: " + date1);

        // Subtracts the number of months
        System.out.println("Date1 after subtracting months: "
                           + date1.minusMonths(-120));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting months: 2028-12-12T13:30:30+05:00

```

**程序二** :

```
// Java program to demonstrate the minusMonths() method
import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse(
                      "2018-12-12T13:30:30+05:00");

        // Prints dates
        System.out.println("Date1: " + date1);

        // Subtracts the number of months
        System.out.println("Date1 after subtracting months: "
                           + date1.minusMonths(140));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting months: 2007-04-12T13:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # minustomorks(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#minusMonths(long))