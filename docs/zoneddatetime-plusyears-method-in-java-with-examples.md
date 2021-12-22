# Java 中的 ZonedDateTime plusYears()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plusyears-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plusyears-method-in-java-with-examples/)

一个**分区时间**类的 **plusYears()** 方法，用于添加该分区时间的年数，并在添加后返回分区时间的副本。此方法在本地时间线上运行，向本地日期时间添加年，添加年后，本地日期时间转换回区域日期时间，使用区域标识获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime plusYears(long years)

```

**参数:**该方法接受单个参数**年**，代表要相加的年，可以是负数。

**返回值:**该方法根据添加了年份的日期时间返回一个**时区**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了 plusYears()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.plusYears() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print instance
        System.out.println("ZonedDateTime before"
                           + " adding years: "
                           + zoneddatetime);

        // add 5 years
        ZonedDateTime returnvalue
            = zoneddatetime.plusYears(5);

        // print result
        System.out.println("ZonedDateTime after "
                           + "adding 5 years: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加年份前的区域添加时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 添加 5 年后的区域添加时间:2023-12-06T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.plusYears() method

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
                           + " adding years: "
                           + zoneddatetime);

        // add 2 years
        ZonedDateTime returnvalue
            = zoneddatetime.plusYears(2);

        // print result
        System.out.println("ZonedDateTime after "
                           + "adding 2 years: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加年份前的区域添加时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 添加 2 年后的区域添加时间:2020-10-25T23:12:31.123+01:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plusYears(长)