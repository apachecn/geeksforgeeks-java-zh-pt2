# Java 中的 ZonedDateTime plusHours()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plushours-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plushours-method-in-java-with-examples/)

**plus shours()**一个 **ZonedDateTime** 类的方法，用于在这个 ZonedDateTime 中添加小时数，并在添加后返回一个 ZonedDateTime 的副本。这在即时时间线上运行，因此增加一个小时将总是一个小时之后的持续时间。增加一小时可能会导致本地日期时间发生一小时以外的变化。
例如，考虑一个时区，如“欧洲/巴黎”，其中秋季夏令时转换意味着本地时间 02:00 到 02:59 发生两次，从夏季的偏移+02:00 变为冬季的+01:00。

*   01:30+02:00 增加一小时将导致 02:30+02:00(均在夏季)
*   02:30+02:00 增加一小时将导致 02:30+01:00(从夏季时间移动到冬季时间)
*   02:30+01:00 增加一小时将导致 03:30+01:00(均在冬季)
*   01:30+02:00 增加三个小时将导致 03:30+01:00(从夏季时间移动到冬季时间)

此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime plusHours(long hours)

```

**参数:**此方法接受单个参数**小时数**，代表要添加的小时数，可以是负数。

**返回值:**该方法返回一个基于该日期时间加上小时的**区域时间**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusHours()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.plusHours() method

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
                           + " adding hours: "
                           + zoneddatetime);

        // add 3 hours
        ZonedDateTime returnvalue
            = zoneddatetime.plusHours(3);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding hours: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加小时前的区域添加时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 添加小时后的区域添加时间:2018-12-06T22:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.plusHours() method

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
                           + " adding hours: "
                           + zoneddatetime);

        // add 20 hours
        ZonedDateTime returnvalue
            = zoneddatetime.plusHours(20);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding hours: "
                           + returnvalue);
    }
}
```

**Output:**

> 新增小时前的区域新增时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 新增小时后的区域新增时间:2018-10-26T19:12:31.123+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plusHours(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#plusHours(long))