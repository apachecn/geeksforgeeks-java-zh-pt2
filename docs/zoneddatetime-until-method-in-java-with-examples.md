# Java 中的 ZonedDateTime 直到()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-until-method-in-java-with-examples/)

**直到()**方法的 **ZonedDateTime** 类用来计算两个 ZonedDateTime 对象之间的时间量，使用的是 TemporalUnit。起点和终点是这个，指定的 ZonedDateTime 作为参数传递。如果结束在开始之前，结果将是否定的。该计算返回一个整数，表示两个区域之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 是结束日期，Exclusive 转换为 ZonedDateTime，unit 是计量金额的单位。

**返回值:**该方法返回该区域开始时间和结束区域结束时间之间的时间。

**异常:**该方法抛出以下异常:

*   日期时间异常–如果无法计算金额，或者结束时间无法转换为区域日期时间。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ZonedDateTime objects
        ZonedDateTime z1
            = ZonedDateTime
                  .parse("2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        ZonedDateTime z2
            = ZonedDateTime
                  .parse("2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // apply until method of ZonedDateTime class
        long result
            = z1.until(z2,
                       ChronoUnit.HOURS);

        // print results
        System.out.println("Result in HOURS: "
                           + result);
    }
}
```

**Output:**

```java
Result in HOURS: -1000

```

**程序 2:**

```java
// Java program to demonstrate
// ZonedDateTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ZonedDateTime objects
        ZonedDateTime z1
            = ZonedDateTime
                  .parse("2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        ZonedDateTime z2
            = ZonedDateTime
                  .parse("2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // applynedDateTime.parseZonedDateTime class
        long result
            = z2.until(z1,
                       ChronoUnit.DAYS);

        // print results
        System.out.println("Result in DAYS: "
                           + result);
    }
}
```

**Output:**

```java
Result in DAYS: 41

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html #直到(java.time.temporal.Temporal，Java . time . temporal unit)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))