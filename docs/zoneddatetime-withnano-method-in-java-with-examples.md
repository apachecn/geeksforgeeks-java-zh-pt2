# Java 中的 ZonedDateTime withNano()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withnano-method-in-java-with-examples/)

**withNano()** 一个 **ZonedDateTime** 类的方法，用于更改此 ZonedDateTime 中的纳米秒，并在此操作后返回 ZonedDateTime 的副本。此方法在本地时间线上操作，更改本地日期时间的时间，在此操作之后，本地日期时间将转换回区域数据时间，使用区域标识来获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime withNano(int nanoOfSecond)

```

**参数:**此方法接受单个参数**毫微秒**，它代表要在结果中设置的毫微秒，0 到 999，999，999。

**返回值:**该方法基于该日期时间返回一个**区域时间**，请求的时间为纳秒。

**异常:**如果纳秒值无效，该方法抛出**日期时间异常**。

下面的程序说明了 withNano()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.withNano() method

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
                           + " alter nanoOfSecond: "
                           + zoneddatetime);

        // alter nanoOfSecond to 12345987
        ZonedDateTime returnvalue
            = zoneddatetime.withNano(12345987);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter nanoOfSecond: "
                           + returnvalue);
    }
}
```

**Output:**

> 更改纳米秒前的时间:2018-12-06t 19:21:12.123+05:30[亚洲/加尔各答]
> 更改纳米秒后的时间:2018-12-06t 19:21:12.012345987+05:30[亚洲/加尔各答]

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.withNano() method

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
                           + " alter nanoOfSecond: "
                           + zoneddatetime);

        // alter nanoOfSecond to 439990000
        ZonedDateTime returnvalue
            = zoneddatetime.withNano(439990000);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter nanoOfSecond: "
                           + returnvalue);
    }
}
```

**Output:**

> 更改纳米秒前的区域更改时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 更改纳米秒后的区域更改时间:2018-10-25t 23:12:31.439990+02:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # with nano(int)