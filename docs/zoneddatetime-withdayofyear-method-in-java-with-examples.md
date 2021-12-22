# Java 中的 ZonedDateTime withDayOfYear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with dayofyear-in-Java-method-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withdayofyear-method-in-java-with-examples/)

**withDayOfYear()** 一个 **ZonedDateTime** 类的方法，用于在此 ZonedDateTime 中更改一年中的某一天，并在此操作后返回 ZonedDateTime 的副本。此方法在本地时间线上操作，更改本地日期时间的一年中的某一天，并且在此操作之后，本地日期时间被转换回区域数据时间，使用区域标识来获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime withDayOfYear(int dayOfYear)

```

**参数:**该方法接受单个参数**dayfyear**，表示在结果中设置的日期，从 1 到 365-366。

**返回值:**该方法根据请求日期的日期时间返回一个**区域日期时间**。

**异常:**如果年中某一天的值无效，或者年中某一天对该年无效，该方法抛出**日期时间异常**。

以下程序举例说明了 withDayOfYear()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.withDayOfYear() method

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
                           + " alter dayOfYear: "
                           + zoneddatetime);

        // alter dayOfYear to 200th day
        ZonedDateTime returnvalue
            = zoneddatetime.withDayOfYear(200);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter dayOfYear: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更日期前的区域变更时间年度:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 变更日期后的区域变更时间年度:2018-07-19T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.withDayOfYear() method

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
                           + " alter dayOfYear: "
                           + zoneddatetime);

        // alter dayOfYear to 365
        ZonedDateTime returnvalue
            = zoneddatetime.withDayOfYear(365);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter dayOfYear: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更日期前的区域变更时间年度:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 变更日期后的区域变更时间年度:2018-12-31T23:12:31.123+01:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # withDayOfYear(int)