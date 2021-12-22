# Java 中的临时调整 lastDayOfMonth()方法，示例

> 原文:[https://www . geeksforgeeks . org/temporaladjasters-lastdayofmonth-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-lastdayofmonth-method-in-java-with-examples/)

**临时调整类**的**last day fmonth()**方法用于返回“每月的最后一天”临时调整对象，该对象返回设置为每月最后一天的新的 Date 对象。

**语法:**

```java
public static TemporalAdjuster lastDayOfMonth()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回月份调整器的最后一天，不为空。

下面的程序说明了临时调整的最后一天()方法:
**程序 1:**

```java
// Java program to demonstrate
// TemporalAdjusters.lastDayOfMonth()

import java.time.LocalDate;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with last day
        // of the month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.lastDayOfMonth();

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2020, 05, 11);
        LocalDate lastDayOfMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("last day of the "
                           + "month for localdate "
                           + localDate + ": "
                           + lastDayOfMonth);
    }
}
```

**Output:**

```java
last day of the month for localdate 2020-05-11: 2020-05-31

```

**程序 2:**

```java
// Java program to demonstrate
// TemporalAdjusters.lastDayOfMonth() method

import java.time.LocalDate;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with last day
        // of the month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters
                  .lastDayOfMonth();

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2010, 12, 29);
        LocalDate lastDayOfMonth
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("last day of the "
                           + "month for localdate "
                           + localDate + ": "
                           + lastDayOfMonth);
    }
}
```

**Output:**

```java
last day of the month for localdate 2010-12-29: 2010-12-31

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/temporalaadjusters . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/TemporalAdjusters.html)