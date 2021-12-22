# Java 中的时间调整第一天第一个()方法，示例

> 原文:[https://www . geeksforgeeks . org/temporaladjasters-first dayofmonth-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-firstdayofmonth-method-in-java-with-examples/)

**临时调整类**的**first day fmonth()**方法用于返回“每月第一天”临时调整对象，该对象返回设置为当月第一天的新的 Date 对象。

**语法:**

```
public static TemporalAdjuster firstDayOfMonth()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回当月第一天的调整器，不为空。

下面的程序说明了临时调整的第一天()方法:
**程序 1:**

```
// Java program to demonstrate
// TemporalAdjusters.firstDayOfMonth()

import java.time.LocalDate;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with first day
        // of month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters
                  .firstDayOfMonth();

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2020, 05, 11);
        LocalDate firstDayOFMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("First day for "
                           + "month for localdate "
                           + localDate + ": "
                           + firstDayOFMonth);
    }
}
```

**Output:**

```
First day for month for localdate 2020-05-11: 2020-05-01

```

**程序 2:**

```
// Java program to demonstrate
// TemporalAdjusters.firstDayOfMonth() method

import java.time.LocalDate;
import java.time.temporal.TemporalAdjuster;
import java.time.temporal.TemporalAdjusters;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with first day
        // of month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters
                  .firstDayOfMonth();

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2010, 12, 29);
        LocalDate firstDayOFMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("First day for "
                           + "month for localdate "
                           + localDate + ": "
                           + firstDayOFMonth);
    }
}
```

**Output:**

```
First day for month for localdate 2010-12-29: 2010-12-01

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/temporalaadjusters . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/TemporalAdjusters.html)