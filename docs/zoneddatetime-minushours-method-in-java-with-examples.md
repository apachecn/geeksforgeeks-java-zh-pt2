# Java 中的 ZonedDateTime minusHours()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-minoshours-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minushours-method-in-java-with-examples/)

**minuthours()**一个 **ZonedDateTime** 类的方法，用于从这个 ZonedDateTime 中减去小时数，并在相减后返回一个 ZonedDateTime 的副本。这在即时时间线上运行，因此减去一小时将总是早一小时的持续时间。减去一小时可能会导致本地日期时间发生一小时以外的变化。
例如，考虑一个时区，如“欧洲/巴黎”，其中秋季夏令时转换意味着本地时间 02:00 到 02:59 发生两次，从夏季的偏移+02:00 变为冬季的+01:00。

*   从 03:30+01:00 减去一小时将得到 02:30+01:00(两者都在冬季)
*   从 02:30+01:00 减去一小时将得到 02:30+02:00(从冬季时间移动到夏季时间)
*   从 02:30+02:00 减去一小时将得到 01:30+02:00(均在夏季)
*   从 03:30+01:00 减去三个小时将得到 01:30+02:00(从冬季时间移动到夏季时间)

此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime minusHours(long hours)

```

**参数:**该方法接受单个参数**小时数**，代表要减去的小时数，可以是负数。

**返回值:**该方法基于该日期时间减去小时数返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 minusHours()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.minusHours() method

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
                           + " subtracting hours: "
                           + zoneddatetime);

        // subtract 3 hours
        ZonedDateTime returnvalue
            = zoneddatetime.minusHours(3);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 3 hours: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去小时前的区域时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 减去 3 小时后的区域时间:2018-12-06T16:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.minusHours() method

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
                           + " subtracting hours: "
                           + zoneddatetime);

        // subtract 20 hours
        ZonedDateTime returnvalue
            = zoneddatetime.minusHours(20);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 20 hours: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去小时前的区域时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 减去 20 小时后的区域时间:2018-10-25T03:12:31.123+02:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # minoshours(长)