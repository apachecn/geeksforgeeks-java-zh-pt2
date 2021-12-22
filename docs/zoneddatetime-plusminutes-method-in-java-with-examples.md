# Java 中的 ZonedDateTime plusMinutes()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plusminutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plusminutes-method-in-java-with-examples/)

**plusMinutes()** 一个 **ZonedDateTime** 类的方法，用于在这个 ZonedDateTime 中添加分钟数，并在添加后返回一个 ZonedDateTime 的副本。该方法在即时时间线上运行，因此增加一分钟将总是一分钟后的持续时间。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime plusMinutes(long minutes)

```

**参数:**此方法接受单个参数**分钟**，代表要添加的分钟数，可以是负数。

**返回值:**该方法返回一个基于该日期时间加上分钟的**区域时间**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusMinutes()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.plusMinutes() method

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
                           + " adding minutes: "
                           + zoneddatetime);

        // add 3 minutes
        ZonedDateTime returnvalue
            = zoneddatetime.plusMinutes(3);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding minutes: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加分钟前的区域添加时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 添加分钟后的区域添加时间:2018-12-06T19:24:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.plusMinutes() method

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
                           + " adding minutes: "
                           + zoneddatetime);

        // add 20 minutes
        ZonedDateTime returnvalue
            = zoneddatetime.plusMinutes(20);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding minutes: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加分钟前的区域添加时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 添加分钟后的区域添加时间:2018-10-25T23:32:31.123+02:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plusMinutes(长)