# 带示例的 Java 中的 ZonedDateTime withHour()方法

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-with our-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-withhour-method-in-java-with-examples/)

**使用一个 **ZonedDateTime** 类的方法来改变这个 ZonedDateTime 中的时间，并在这个操作之后返回一个 ZonedDateTime 的副本。此方法在本地时间线上操作，更改本地日期时间的时间，在此操作之后，本地日期时间将转换回区域数据时间，使用区域标识来获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。**

**语法:**

```java
public ZonedDateTime withHour(int hour)

```

**参数:**该方法接受单个参数**小时**，表示在结果中设置的一天中的小时，从 0 到 23。

**返回值:**该方法根据该日期时间和请求的小时数返回一个**区域时间**。

**异常:**如果小时值无效，该方法抛出**日期时间异常**。

下面的程序说明了 withHour()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.withHour() method

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
                           + " alter hour: "
                           + zoneddatetime);

        // alter hour to 20
        ZonedDateTime returnvalue
            = zoneddatetime.withHour(20);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter hour: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更时间前的区域变更时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 变更时间后的区域变更时间:2018-12-06T20:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.withHour() method

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
                           + " alter hour: "
                           + zoneddatetime);

        // alter hour to 0
        ZonedDateTime returnvalue
            = zoneddatetime.withHour(0);

        // print result
        System.out.println("ZonedDateTime after "
                           + "alter hour: "
                           + returnvalue);
    }
}
```

**Output:**

> 变更时间前区域变更时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 变更时间后区域变更时间:2018-10-25T00:12:31.123+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # withour(int)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#withHour(int))