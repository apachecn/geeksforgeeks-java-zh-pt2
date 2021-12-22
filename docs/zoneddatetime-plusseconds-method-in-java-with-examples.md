# Java 中的 ZonedDateTime plusSeconds()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-plus seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-plusseconds-method-in-java-with-examples/)

**plusSeconds()** 一个 **ZonedDateTime** 类的方法，用于在此 ZonedDateTime 中添加秒数，并在添加后返回 ZonedDateTime 的副本。此方法在即时时间线上工作，添加一秒将返回一秒后的时间线。请注意，该方法不同于按天、月和年使用的方法。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public ZonedDateTime plusSeconds(long seconds)

```

**参数:**此方法接受单个参数**秒**，代表要添加的秒，可以是负数。

**返回值:**该方法根据添加了秒数的日期时间返回一个**区域时间**。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了 plusSeconds()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.plusSeconds() method

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
                           + " adding seconds: "
                           + zoneddatetime);

        // add 3002 seconds
        ZonedDateTime returnvalue
            = zoneddatetime.plusSeconds(3002);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding seconds: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加秒之前的区域添加时间:2018-12-06T19:21:12.123+05:30【亚洲/加尔各答】
> 添加秒之后的区域添加时间:2018-12-06T20:11:14.123+05:30【亚洲/加尔各答】

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.plusSeconds() method

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
                           + " adding seconds: "
                           + zoneddatetime);

        // add 52 seconds
        ZonedDateTime returnvalue
            = zoneddatetime.plusSeconds(52);

        // print result
        System.out.println("ZonedDateTime after "
                           + " adding seconds: "
                           + returnvalue);
    }
}
```

**Output:**

> 添加秒前的区域添加时间:2018-10-25T23:12:31.123+02:00【欧洲/巴黎】
> 添加秒后的区域添加时间:2018-10-25T23:13:23.123+02:00【欧洲/巴黎】

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # plus seconds(长)