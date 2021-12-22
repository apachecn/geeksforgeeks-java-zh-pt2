# Java 中的 ZonedDateTime 天数()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-mindays-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minusdays-method-in-java-with-examples/)

**天数()**一个 **ZonedDateTime** 类的方法，用于从这个 ZonedDateTime 中减去指定的天数，并返回一个 ZonedDateTime 的副本。此方法从本地日期时间中减去作为参数传递的天数，然后将其转换回区域数据时间，使用区域标识获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime minusDays(long days)

```

**参数:**该方法接受单个参数**天数**，代表要减去的天数，可以是负数。

**返回值:**该方法根据减去天数后的日期时间返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了天数()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.minusDays() method

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
                           + " subtracting days: "
                           + zoneddatetime);

        // subtract 13 days
        ZonedDateTime returnvalue
            = zoneddatetime.minusDays(13);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 13 days: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去天数前的区域时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 减去 13 天后的区域时间:2018-11-23T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.minusDays() method

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
                           + " subtracting days: "
                           + zoneddatetime);

        // subtract 22 days
        ZonedDateTime returnvalue
            = zoneddatetime.minusDays(20);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 24 days: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去天数前的分区时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 减去 24 天后的分区时间:2018-10-05T23:12:31.123+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # mindsdays(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minusDays(long))。html #不稳定年份(长)