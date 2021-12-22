# Java 中的临时调整第一个月()方法，示例

> 原文:[https://www . geesforgeks . org/temporaladjasters-first in month-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-firstinmonth-method-in-java-with-examples/)

**时间调整器类**的 **firstInMonth(DayOfWeek)** 方法用于返回一个时间调整器对象，该对象可用于获取一个新的 date 对象，该对象是同一个月的第一个日期，其匹配的 DayOfWeek 作为参数从应用此时间调整器的任何 Date 对象中传递。

**语法:**

```
public static TemporalAdjuster
       firstInMonth(DayOfWeek dayOfWeek)

```

**参数:**该方法接受**日期/星期**，可用于获取一个新的日期对象，该日期对象是具有相同匹配日期/星期的同一个月的第一个日期。

**返回值:**此方法返回月内第一个调整器，不为空。

下面的程序说明了临时调整.第一个月()方法:
**程序 1:**

```
// Java program to demonstrate
// TemporalAdjusters.firstInMonth()

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with
        // the first in month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.firstInMonth(
                DayOfWeek.SUNDAY);

        // using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2023, 10, 11);
        LocalDate firstInMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println(
            "First date in month having"
            + " sunday for localdate "
            + localDate + " is: "
            + firstInMonth);
    }
}
```

**Output:**

```
First date in month having sunday for localdate 2023-10-11 is: 2023-10-01

```

**程序 2:**

```
// Java program to demonstrate
// TemporalAdjusters.firstInMonth() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with
        // the first in month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.firstInMonth(
                DayOfWeek.TUESDAY);

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2023, 10, 11);
        LocalDate firstInMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println(
            "First date in a month having"
            + " TUESDAY for localdate "
            + localDate + " is: "
            + firstInMonth);
    }
}
```

**Output:**

```
First date in a month having TUESDAY for localdate 2023-10-11 is: 2023-10-03

```

参考资料:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporalaadjusters . html # first in month(Java . time . dayofweek)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/TemporalAdjusters.html#firstInMonth(java.time.DayOfWeek))