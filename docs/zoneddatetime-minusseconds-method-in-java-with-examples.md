# Java 中的 ZonedDateTime minusSeconds()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-mins seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minusseconds-method-in-java-with-examples/)

**minusSeconds()** 一个 **ZonedDateTime** 类的方法，用于从这个 ZonedDateTime 中减去秒数，并在相减后返回一个 ZonedDateTime 的副本。此方法在即时时间线上工作，减去一秒将返回早一秒的时间线。请注意，该方法不同于按天、月和年使用的方法。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime minusSeconds(long seconds)

```

**参数:**该方法接受单个参数**秒**，代表要减去的秒，可以是负数。

**返回值:**该方法根据该日期时间减去秒数返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了负秒()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.minusSeconds() method

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
                           + " subtracting seconds: "
                           + zoneddatetime);

        // subtract 100 seconds
        ZonedDateTime returnvalue
            = zoneddatetime.minusSeconds(100);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 100 seconds: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去 100 秒前的 ZonedDateTime:2018-12-06t 19:21:12.123+05:30【亚洲/加尔各答】
> 减去 100 秒后的 ZonedDateTime:2018-12-06t 19:19:32.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.minusSeconds() method

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
                           + " subtracting seconds: "
                           + zoneddatetime);

        // subtract -22 seconds
        ZonedDateTime returnvalue
            = zoneddatetime.minusSeconds(-22);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting -22 seconds: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去秒前的区域时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 减去-22 秒后的区域时间:2018-10-25T23:12:53.123+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # minseconds(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minusSeconds(long))