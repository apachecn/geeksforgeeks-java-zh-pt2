# Java 中的 ZonedDateTime withYear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with year-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withyear-method-in-java-with-examples/)

**withYear()** 一个 **ZonedDateTime** 类的方法，用于在这个 ZonedDateTime 中更改年份，并在这个操作之后返回一个 ZonedDateTime 的副本。此方法在本地时间线上操作，更改本地日期时间的年份，在此操作之后，本地日期时间将转换回区域数据时间，使用区域标识来获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime withYear(int year)

```

**参数:**该方法接受单个参数**年份**，代表要在结果中设置的年份，从 MIN_YEAR 到 MAX_YEAR。

**返回值:**该方法根据请求年份的日期时间返回一个**时区**。

**异常:**如果年份值无效，此方法抛出**日期时间异常**。

下面的程序说明了 withYear()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.withYear() method

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
                           + " alter year: "
                           + zoneddatetime);

        // alter year to 2200
        ZonedDateTime returnvalue
            = zoneddatetime.withYear(2200);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter year: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更年前区域变更时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 变更年后区域变更时间:2200-12-06T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.withYear() method

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
                           + " alter year: "
                           + zoneddatetime);

        // alter year to 1923
        ZonedDateTime returnvalue
            = zoneddatetime.withYear(1923);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter year: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更年前区域变更时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 变更年后区域变更时间:1923-10-25T23:12:31.123Z【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with year(int)