# Java 中的 OffsetDateTime plusMonths()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-plusmonths-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-plusmonths-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **plusMonths()** 方法返回这个 OffsetDateTime 的一个副本，指定的月数被添加到解析的日期和时间中。

**语法:**

```
public OffsetDateTime plusMonths(long months)
```

**参数:**该方法接受单个参数**月份**，该参数指定要添加到解析日期的月份。它也可以是负的，在这种情况下，它会减去月数。

**返回值:**根据这个日期时间返回一个偏置日期时间，加上月份，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了 *plusMonths()* 方法:

**程序 1:**

```
// Java program to demonstrate the plusMonths() method

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
        System.out.println("Date1 after adding months: "
                           + date1.plusMonths(-120));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding months: 2008-12-12T13:30:30+05:00

```

**程序二** :

```
// Java program to demonstrate the plusMonths() method

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
        System.out.println("Date1 after adding months: "
                           + date1.plusMonths(140));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding months: 2030-08-12T13:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # plusMonths(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#plusMonths(long))