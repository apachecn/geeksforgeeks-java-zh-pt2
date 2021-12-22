# Java 中的 ZonedDateTime MINUS()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-mins years-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minusyears-method-in-java-with-examples/)

一个**分区时间**类的 **minusYears()** 方法，用于从这个分区时间中减去年数，并在相减后返回一个分区时间的副本。此方法在本地时间线上运行，从本地日期时间中减去年，减去年后，本地日期时间将转换回区域数据时间，使用区域标识获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime minusYears(long years)

```

**参数:**该方法接受单个参数**年**，代表要减去的年，可以是负数。

**返回值:**该方法根据该日期时间减去年数，返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了负年()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.minusYears() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print instance
        System.out.println("ZonedDateTime before"
                           + " subtracting years: "
                           + zoneddatetime);

        // subtract 15 years
        ZonedDateTime returnvalue
            = zoneddatetime.minusYears(5);

        // print result
        System.out.println("ZonedDateTime after "
                           + "subtracting 15 years: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去年份前的区域时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 减去 15 年后的区域时间:2013-12-06T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.minusYears() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // print instance
        System.out.println("ZonedDateTime before"
                           + " subtracting years: "
                           + zoneddatetime);

        // subtract 12 years
        ZonedDateTime returnvalue
            = zoneddatetime.minusYears(12);

        // print result
        System.out.println("ZonedDateTime after "
                           + "subtracting 12 years: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去年份前的区域时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 减去 12 年后的区域时间:2006-10-25T23:12:31.123+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # mins years(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minusYears(long))