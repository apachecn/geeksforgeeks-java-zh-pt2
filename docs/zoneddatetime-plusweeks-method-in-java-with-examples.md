# Java 中的 ZonedDateTime plusWeeks()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plusweeks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plusweeks-method-in-java-with-examples/)

**plusWeeks()** 一个 **ZonedDateTime** 类的方法，用于在这个 ZonedDateTime 中添加周数，并在添加后返回一个 ZonedDateTime 的副本。此方法在本地时间线上运行，向本地日期时间添加周，添加周之后，本地日期时间转换回区域日期时间，使用区域标识获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime plusWeeks(long weeks)

```

**参数:**此方法接受单个参数**周**，代表要添加的周，可以是负数。

**返回值:**该方法根据添加了周的日期时间返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了 plusWeeks()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.plusWeeks() method

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
                           + " adding weeks: "
                           + zoneddatetime);

        // add 10 weeks
        ZonedDateTime returnvalue
            = zoneddatetime.plusWeeks(10);

        // print result
        System.out.println("ZonedDateTime after "
                           + "adding 10 weeks: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加周之前的区域添加时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 添加 10 周之后的区域添加时间:2019-02-14T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.plusWeeks() method

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
                           + " adding weeks: "
                           + zoneddatetime);

        // add 2 weeks
        ZonedDateTime returnvalue
            = zoneddatetime.plusWeeks(2);

        // print result
        System.out.println("ZonedDateTime after "
                           + "adding 2 weeks: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加周之前的区域添加时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 添加 2 周之后的区域添加时间:2018-11-08T23:12:31.123+01:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plusWeeks(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#plusWeeks(long))