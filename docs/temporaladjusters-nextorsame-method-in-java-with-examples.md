# Java 中的 TemporalAdjusters nextOrSame()方法，示例

> 原文:[https://www . geeksforgeeks . org/temporaladjasters-nextorsame-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-nextorsame-method-in-java-with-examples/)

**时间调整类**的**next or name(DayOfWeek)**方法用于返回下一个或同一个 DayOfWeek 时间调整对象，该对象可用于从应用此时间调整的任何日期对象中获取下一个或同一个日期对象，该日期对象具有指定为参数的相同 DayOfWeek。

**语法:**

```java
public static TemporalAdjuster
       nextOrSame(DayOfWeek dayOfWeek)

```

**参数:**该方法接受**日期/星期**，该日期/星期可用于获取新的日期对象，该日期对象是具有相同日期/星期的下一个或相同日期

**返回值:**此方法返回下一个或同一个 DayOfWeek 调整器。

下面的程序说明了临时调整.下一个或名称()方法:
**程序 1:**

```java
// Java program to demonstrate
// TemporalAdjusters.nextOrSame()

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with the nextOrSame in
        // month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.nextOrSame(DayOfWeek.WEDNESDAY);

        // using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2020, 10, 31);
        LocalDate nextOrSameDOW
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("Next or same date having "
                           + "WEDNESDAY for localdate "
                           + localDate + " is: "
                           + nextOrSameDOW);
    }
}
```

**Output:**

```java
Next or same date having WEDNESDAY for localdate 2020-10-31 is: 2020-11-04

```

**程序 2:**

```java
// Java program to demonstrate
// TemporalAdjusters.nextOrSame() method

import java.time.*;
import java.time.temporal.TemporalAdjuster;
import java.time.temporal.TemporalAdjusters;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with the
        // nextOrSame day of week adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters
                  .nextOrSame(
                      DayOfWeek.THURSDAY);

        // using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2020, 02, 27);
        LocalDate nextOrSameDOW
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("Next or same date having "
                           + "WEDNESDAY for localdate "
                           + localDate + " is: "
                           + nextOrSameDOW);
    }
}
```

**Output:**

```java
Next or same date having WEDNESDAY for localdate 2020-02-27 is: 2020-02-27

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporalaadjusters . html # nextOrSame(Java . time . dayofweek)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/TemporalAdjusters.html#nextOrSame(java.time.DayOfWeek))