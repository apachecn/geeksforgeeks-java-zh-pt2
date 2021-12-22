# Java 中的 temporalaadjusters first dayofnextmonth()方法，带示例

> 原文:[https://www . geesforgeks . org/temporalaadjusters-first dayofnextmonth-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-firstdayofnextmonth-method-in-java-with-examples/)

一个**临时调整类**的 **firstDayOfNextMonth()** 方法用于返回“下个月的第一天”临时调整对象，该对象返回一个设置为下个月的第一天的新的 Date 对象。

**语法:**

```
public static TemporalAdjuster firstDayOfNextMonth()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回下个月的第一天调整器，不为空。

下面的程序说明了临时调整的第一天第一个月()方法:
**程序 1:**

```
// Java program to demonstrate
// TemporalAdjusters.firstDayOfNextMonth()

import java.time.LocalDate;
import java.time.temporal.TemporalAdjuster;
import java.time.temporal.TemporalAdjusters;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with first day
        // of next month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.firstDayOfNextMonth();

        // using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2020, 05, 11);
        LocalDate firstDayOfNextMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("First day of next "
                           + "month for localdate "
                           + localDate + ": "
                           + firstDayOfNextMonth);
    }
}
```

**Output:**

```
First day of next month for localdate 2020-05-11: 2020-06-01

```

**程序 2:**

```
// Java program to demonstrate
// TemporalAdjusters.firstDayOfNextMonth() method

import java.time.LocalDate;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with first day
        // of next month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters
                  .firstDayOfNextMonth();

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2010, 12, 29);
        LocalDate firstDayOfNextMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println(
            "First day of next "
            + "month for localdate "
            + localDate + ": "
            + firstDayOfNextMonth);
    }
}
```

**Output:**

```
First day of next month for localdate 2010-12-29: 2011-01-01

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/temporalaadjusters . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/TemporalAdjusters.html)