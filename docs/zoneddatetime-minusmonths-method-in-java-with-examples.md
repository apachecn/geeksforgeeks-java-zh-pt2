# Java 中的 ZonedDateTime minutations()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-mins months-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minusmonths-method-in-java-with-examples/)

**minusMonths()** 一个 **ZonedDateTime** 类的方法，用于减去该 ZonedDateTime 中的月数，并在相减后返回 ZonedDateTime 的副本。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ZonedDateTime minusMonths(long months)

```

**参数:**该方法接受单个参数**月份**，代表要减去的月份，可以是负数。

**返回值:**该方法返回一个基于该日期时间的**区域时间**，减去月份，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了最小月()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.minusMonths() method

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
                           + " subtracting months: "
                           + zoneddatetime);

        // subtract 10 months
        ZonedDateTime returnvalue
            = zoneddatetime.minusMonths(10);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 10 months: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去月份前的区域时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 减去 10 个月后的区域时间:2018-02-06T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.minusMonths() method

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
                           + " subtracting months: "
                           + zoneddatetime);

        // subtract 2 months
        ZonedDateTime returnvalue
            = zoneddatetime.minusMonths(2);

        // print result
        System.out.println("ZonedDateTime after "
                           + " subtracting 2 months: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去月份前的区域时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 减去 2 个月后的区域时间:2018-08-25T23:12:31.123+02:00【欧洲/巴黎】

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # MINUS months(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minusMonths(long))