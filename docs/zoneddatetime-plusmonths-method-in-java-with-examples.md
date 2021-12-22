# Java 中的 ZonedDateTime plusMonths()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plusmonths-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plusmonths-method-in-java-with-examples/)

**plusMonths()** 一个 **ZonedDateTime** 类的方法，用于添加该 ZonedDateTime 中的月数，并在添加后返回 ZonedDateTime 的副本。此方法在本地时间线上运行，向本地日期时间添加月份，添加月份后，本地日期时间转换回区域日期时间，使用区域标识获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime plusMonths(long months)

```

**参数:**此方法接受单个参数**月份**，代表要添加的月份，可以是负数。

**返回值:**该方法根据添加了月份的日期时间返回一个**区域日期时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusMonths()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.plusMonths() method

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
                           + " adding months: "
                           + zoneddatetime);

        // add 3 months
        ZonedDateTime returnvalue
            = zoneddatetime.plusMonths(3);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding months: "
                           + returnvalue);
    }
}
```

**Output:**

```
ZonedDateTime before adding months: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ZonedDateTime after  adding months: 2019-03-06T19:21:12.123+05:30[Asia/Calcutta]

```

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.plusMonths() method

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
                           + " adding months: "
                           + zoneddatetime);

        // add 20 months
        ZonedDateTime returnvalue
            = zoneddatetime.plusMonths(20);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding months: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加月份前的区域添加时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 添加月份后的区域添加时间:2020-06-25T23:12:31.123+02:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plusMonths(长)