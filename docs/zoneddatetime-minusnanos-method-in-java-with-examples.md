# Java 中的 ZonedDateTime 亚纳米()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-mins nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minusnanos-method-in-java-with-examples/)

**nanos()**一个 **ZonedDateTime** 类的方法，用于从这个 ZonedDateTime 中减去纳秒数，并在相减后返回一个 ZonedDateTime 的副本。此方法在即时时间线上工作，减去一纳秒将返回早一纳秒的时间线。请注意，该方法不同于按天、月和年使用的方法。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime minusNanos(long nanoseconds)

```

**参数:**该方法接受单个参数**纳秒**，代表要减去的纳秒，可以是负数。

**返回值:**该方法基于该日期时间减去纳秒后返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了亚纳米()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.minusNanos() method

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
                           + " subtracting nanoseconds: "
                           + zoneddatetime);

        // subtract 30000000 nanoseconds
        ZonedDateTime returnvalue
            = zoneddatetime.minusNanos(30000000);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 30000000 nanoseconds: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去纳秒前的 ZonedDateTime:2018-12-06t 19:21:12.123+05:30【亚洲/加尔各答】
> 减去 30000000 纳秒后的 ZonedDateTime:2018-12-06t 19:21:12.093+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.minusNanos() method

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
                           + " subtracting nanoseconds: "
                           + zoneddatetime);

        // subtract 52000000 nanoseconds
        ZonedDateTime returnvalue
            = zoneddatetime.minusNanos(52000000);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 52000000 nanoseconds: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去纳秒前的 ZonedDateTime:2018-10-25t 23:12:31.123+02:00【欧洲/巴黎】
> 减去 52000000 纳秒后的 ZonedDateTime:2018-10-25t 23:12:31.071+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # mins nanos(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minusNanos(long))