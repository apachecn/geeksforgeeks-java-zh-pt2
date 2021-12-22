# Java 中的 ZonedDateTime withMinute()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with minute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withminute-method-in-java-with-examples/)

**withMinute()** 一个 **ZonedDateTime** 类的方法，用于在此 ZonedDateTime 中更改分钟，并在此操作后返回 ZonedDateTime 的副本。此方法在本地时间线上操作，更改本地日期时间的分钟，并且在此操作之后，本地日期时间将转换回区域数据时间，使用区域标识来获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime withMinute(int minute)

```

**参数:**该方法接受单个参数**分钟**，表示在结果中设置的小时分钟，从 0-59。

**返回值:**该方法根据该日期时间和请求的分钟数返回一个**区域时间**。

**异常:**如果小时分钟值无效，或者如果小时分钟对年无效，则此方法抛出**日期时间异常**。

下面的程序说明了 withMinute()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.withMinute() method

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
                           + " alter minute: "
                           + zoneddatetime);

        // alter minute to 2
        ZonedDateTime returnvalue
            = zoneddatetime.withMinute(2);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter minute: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更分钟前区域变更时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 变更分钟后区域变更时间:2018-12-06T19:02:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.withMinute() method

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
                           + " alter minute: "
                           + zoneddatetime);

        // alter minute to 50
        ZonedDateTime returnvalue
            = zoneddatetime.withMinute(50);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter minute: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更分钟前区域变更时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 变更分钟后区域变更时间:2018-10-25T23:50:31.123+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with minute(int)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#withMinute(int))