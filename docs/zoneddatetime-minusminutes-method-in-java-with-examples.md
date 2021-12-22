# Java 中的 ZonedDateTime minusMinutes()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-mins minutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minusminutes-method-in-java-with-examples/)

**minutations()**一个 **ZonedDateTime** 类的方法，用于从这个 ZonedDateTime 中减去分钟数，并在相减后返回一个 ZonedDateTime 的副本。该方法在即时时间线上运行，因此减去一分钟将总是早一分钟的持续时间。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime minusMinutes(long minutes)

```

**参数:**该方法接受单个参数**分钟**，代表要减去的分钟数，可以是负数。

**返回值:**该方法返回一个基于该日期时间减去分钟的**区域时间**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了分钟数()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.minusMinutes() method

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
                           + " subtracting minutes: "
                           + zoneddatetime);

        // subtract 15 minutes
        ZonedDateTime returnvalue
            = zoneddatetime.minusMinutes(15);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 15 minutes: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去 15 分钟前的区域时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 减去 15 分钟后的区域时间:2018-12-06T19:06:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.minusMinutes() method

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
                           + " subtracting minutes: "
                           + zoneddatetime);

        // subtract 20 minutes
        ZonedDateTime returnvalue
            = zoneddatetime.minusMinutes(20);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 20 minutes: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去分钟前的区域时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 减去 20 分钟后的区域时间:2018-10-25T22:52:31.123+02:00【欧洲/巴黎】

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # minutes(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minusMinutes(long))