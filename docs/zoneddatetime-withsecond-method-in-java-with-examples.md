# Java 中的 ZonedDateTime withSecond()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with second-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withsecond-method-in-java-with-examples/)

**withSecond()** 方法的一个 **ZonedDateTime** 类，用于改变这个 ZonedDateTime 中的分钟数，并在这个操作之后返回一个 ZonedDateTime 的副本。此方法在本地时间线上操作，更改本地日期时间的分钟秒字段，并且在此操作之后，本地日期时间将转换回区域数据时间，使用区域标识来获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime withSecond(int second)

```

**参数:**该方法接受单个参数**秒**，表示在结果中设置的分钟秒，从 0 到 59。

**返回值:**该方法根据请求秒的日期时间返回一个**区域时间**。

**异常:**如果第二个值无效，该方法抛出**日期时间异常**。

下面的程序说明了 withSecond()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.withSecond() method

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
                           + " alter second: "
                           + zoneddatetime);

        // alter second to 40
        ZonedDateTime returnvalue
            = zoneddatetime.withSecond(40);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter second: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更秒前区域变更时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 变更秒后区域变更时间:2018-12-06T19:21:40.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.withSecond() method

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
                           + " alter second: "
                           + zoneddatetime);

        // alter second to 0
        ZonedDateTime returnvalue
            = zoneddatetime.withSecond(0);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter second: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更秒前区域变更时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 变更秒后区域变更时间:2018-10-25T23:12:00.123+02:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with second(int)