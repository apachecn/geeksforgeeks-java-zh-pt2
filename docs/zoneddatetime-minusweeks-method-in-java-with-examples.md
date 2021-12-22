# Java 中的 ZonedDateTime minusWeeks()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-mins weeks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minusweeks-method-in-java-with-examples/)

**minutweeks()**一个 **ZonedDateTime** 类的方法，用于从这个 ZonedDateTime 中减去周数，并在相减后返回一个 ZonedDateTime 的副本。此方法在本地时间线上运行，从本地日期时间中减去周，在减去周之后，本地日期时间将转换回区域数据时间，使用区域标识获取偏移量。当转换回 ZonedDateTime 时，如果本地日期时间重叠，那么如果可能，将保留偏移，否则，将使用较早的偏移。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime minusWeeks(long weeks)

```

**参数:**该方法接受单个参数**周**，代表要减去的周，可以是负数。

**返回值:**该方法基于减去周的日期时间返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了负周()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.minusWeeks() method

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
                           + " subtracting weeks: "
                           + zoneddatetime);

        // subtract 10 weeks
        ZonedDateTime returnvalue
            = zoneddatetime.minusWeeks(10);

        // print result
        System.out.println("ZonedDateTime after "
                           + "subtracting 10 weeks: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去 10 周之前的区域时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 减去 10 周之后的区域时间:2018-09-27T19:21:12.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.minusWeeks() method

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
                           + " subtracting weeks: "
                           + zoneddatetime);

        // subtract 2 weeks
        ZonedDateTime returnvalue
            = zoneddatetime.minusWeeks(2);

        // print result
        System.out.println("ZonedDateTime after "
                           + "subtracting 2 weeks: "
                           + returnvalue);
    }
}
```

**Output:**

> 减去周数前的区域时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 减去 2 周后的区域时间:2018-10-11T23:12:31.123+02:00【欧洲/巴黎】

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # mins weeks(长)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minusWeeks(long))