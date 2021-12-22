# Java 中的 ZonedDateTime withMonth()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withmonth-method-in-java-with-examples/)

**withMonth()** 一个 **ZonedDateTime** 类的方法，用于在此 ZonedDateTime 中更改年月，并在此操作后返回 ZonedDateTime 的副本。此方法在本地时间线上操作，更改本地日期时间的月份，在此操作之后，本地日期时间将转换回区域日期时间，使用区域标识来获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime withMonth(int month)

```

**参数:**该方法接受单个参数**月**，表示在结果中设置的月份，从 1 月 1 日到 12 月 12 日。

**返回值:**该方法根据该日期时间和请求的月份返回一个**区域日期时间**。

**异常:**如果月份值无效，此方法抛出**日期时间异常**。

下面的程序说明了 withMonth()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.withMonth() method

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
                           + " alter month: "
                           + zoneddatetime);

        // alter month to 5(May)
        ZonedDateTime returnvalue
            = zoneddatetime.withMonth(5);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter month: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更月前区域变更时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 变更月后区域变更时间:2018-05-06T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.withMonth() method

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
                           + " alter month: "
                           + zoneddatetime);

        // alter month to 12(december)
        ZonedDateTime returnvalue
            = zoneddatetime.withMonth(12);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter month: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更月前区域变更时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 变更月后区域变更时间:2018-12-25T23:12:31.123+01:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with month(int)