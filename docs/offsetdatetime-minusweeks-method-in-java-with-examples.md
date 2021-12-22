# Java 中的 OffsetDateTime minusWeeks()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-mins weeks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-minusweeks-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **minusWeeks()** 方法返回这个 OffsetDateTime 的一个副本，从解析的日期和时间中减去指定的周数。

**语法:**

```java
public OffsetDateTime minusWeeks(long weeks)

```

**参数:**该方法接受单个参数**周数**，该参数指定要从解析的日期中减去的周数。它也可以是负数，在这种情况下，它会加上周数。

**返回值:**根据这个日期时间返回一个 OffsetDateTime，减去周，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了*次周()*方法:

**程序 1:**

```java
// Java program to demonstrate the minusWeeks() method

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

        // Subtracts the number of weeks
        System.out.println("Date1 after subtracting weeks: "
                           + date1.minusWeeks(-120));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting weeks: 2021-03-31T13:30:30+05:00

```

**程序二:**

```java
// Java program to demonstrate the minusWeeks() method

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

        // Subtracts the number of weeks
        System.out.println("Date1 after subtracting weeks: "
                           + date1.minusWeeks(140));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting weeks: 2016-04-06T13:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # mins weeks(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#minusWeeks(long))