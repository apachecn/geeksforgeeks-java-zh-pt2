# Java 中的 temporalaadjusters first dayofnextyear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/temporaladjasters-first dayofnextyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-firstdayofnextyear-method-in-java-with-examples/)

**时间调整类**的 **firstDayOfNextYear()** 方法用于返回“明年第一天”时间调整对象，该对象返回设置为明年第一天的新日期对象。

**语法:**

```
public static TemporalAdjuster firstDayOfNextYear()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回明年调整器的第一天，不为空。

下面的程序说明了临时调整时间。第一天第一年()方法:
**程序 1:**

```
// Java program to demonstrate
// TemporalAdjusters.firstDayOfNextYear()

import java.time.LocalDate;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with first day
        // of next year adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.firstDayOfNextYear();

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2020, 05, 11);
        LocalDate firstDayOfNextYear
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("First day of next "
                           + "year for localdate "
                           + localDate +": "
                           + firstDayOfNextYear);
    }
}
```

**Output:**

```
First day of next year for localdate 2020-05-11: 2021-01-01

```

**程序 2:**

```
// Java program to demonstrate
// TemporalAdjusters.firstDayOfNextYear() method

import java.time.LocalDate;
import java.time.temporal.TemporalAdjuster;
import java.time.temporal.TemporalAdjusters;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with first day
        // of next year adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters
                  .firstDayOfNextYear();

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2010, 12, 29);
        LocalDate firstDayOfNextYear
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("First day of next "
                           + "year for localdate :"
                           + localDate +": "
                           + firstDayOfNextYear);
    }
}
```

**Output:**

```
First day of next year for localdate :2010-12-29: 2011-01-01

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/temporalaadjusters . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/TemporalAdjusters.html)