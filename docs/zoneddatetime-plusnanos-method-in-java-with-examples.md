# Java 中的 ZonedDateTime plusNanos()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plusnanos-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plusnanos-method-in-java-with-examples/)

**plusNanos()** 一个 **ZonedDateTime** 类的方法，用于在这个 ZonedDateTime 中添加纳秒数，并在添加后返回一个 ZonedDateTime 的副本。这种方法工作在瞬时时间线上，加一纳秒返回一纳秒后的时间线。请注意，该方法不同于按天、月和年使用的方法。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime plusNanos(long nanoseconds)

```

**参数:**该方法接受单个参数**纳秒**，代表要相加的纳秒，可以是负数。

**返回值:**该方法根据添加了纳秒的日期时间返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusNanos()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.plusNanos() method

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
                           + " adding nanoseconds: "
                           + zoneddatetime);

        // add 30000000 nanoseconds
        ZonedDateTime returnvalue
            = zoneddatetime.plusNanos(30000000);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding nanoseconds: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加纳秒前的 ZonedDateTime:2018-12-06t 19:21:12.123+05:30【亚洲/加尔各答】
> 添加纳秒后的 ZonedDateTime:2018-12-06t 19:21:12.153+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.plusNanos() method

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
                           + " adding nanoseconds: "
                           + zoneddatetime);

        // add 5200000 nanoseconds
        ZonedDateTime returnvalue
            = zoneddatetime.plusNanos(5200000);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding nanoseconds: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加纳秒前的区域添加时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 添加纳秒后的区域添加时间:2018-10-25t 23:12:31.128200+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plusNanos(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#plusNanos(long))