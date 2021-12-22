# Java 中的临时调整持续时间()方法，示例

> 原文:[https://www . geeksforgeeks . org/temporaladjasters-lastin month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-lastinmonth-method-in-java-with-examples/)

**时间调整器类**的 **lastInMonth(DayOfWeek)** 方法用于返回一个时间调整器对象，该对象可用于获取一个新的 date 对象，该对象是同一个月的最后一个日期，其匹配的 DayOfWeek 作为参数从应用此时间调整器的任何 Date 对象中传递。

**语法:**

```
public static TemporalAdjuster lastInMonth(DayOfWeek dayOfWeek)

```

**参数:**该方法接受**日期/星期**，可用于获取一个新的日期对象，该对象是具有相同匹配日期/星期的同一个月的最后一个日期。

**返回值:**此方法返回月内最后一个调整器，不为空。

下面的程序说明了临时调整.最后一个月()方法:
**程序 1:**

```
// Java program to demonstrate
// TemporalAdjusters.lastInMonth()

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with
        // the last in month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.lastInMonth(
                DayOfWeek.SUNDAY);

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(1998, 10, 31);
        LocalDate lastInMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println(
            "last date in month having"
            + " sunday for localdate "
            + localDate + " is: "
            + lastInMonth);
    }
}
```

**Output:**

```
last date in month having sunday for localdate 1998-10-31 is: 1998-10-25

```

**程序 2:**

```
// Java program to demonstrate
// TemporalAdjusters.lastInMonth() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with
        // the last in month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.lastInMonth(
                DayOfWeek.TUESDAY);

        // using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2029, 12, 11);
        LocalDate lastInMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println(
            "The last date in a month "
            + "having TUESDAY for localdate "
            + localDate + " is: "
            + lastInMonth);
    }
}
```

**Output:**

```
The last date in a month having TUESDAY for localdate 2029-12-11 is: 2029-12-25

```

参考资料:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporalaadjusters . html # lastInMonth(Java . time . dayofweek)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/TemporalAdjusters.html#lastInMonth(java.time.DayOfWeek))