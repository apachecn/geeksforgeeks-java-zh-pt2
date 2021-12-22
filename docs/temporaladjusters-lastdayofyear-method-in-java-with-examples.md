# Java 中的临时调整器 lastDayOfYear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/temporaladjasters-lastdayofyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-lastdayofyear-method-in-java-with-examples/)

**临时调整类**的**last day fyeear()**方法用于返回“一年中的最后一天”临时调整对象，该对象返回设置为一年中最后一天的新的 Date 对象。

**语法:**

```java
public static TemporalAdjuster lastDayOfYear()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回年度调整器的最后一天，不为空。

下面的程序说明了临时调整时间的方法:
**程序 1:**

```java
// Java program to demonstrate
// TemporalAdjusters.lastDayOfYear()

import java.time.LocalDate;
import java.time.temporal.TemporalAdjuster;
import java.time.temporal.TemporalAdjusters;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with last day
        // of the year adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.lastDayOfYear();

        // using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2023, 10, 11);
        LocalDate lastDayOfYear
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("last day of the "
                           + "year for localdate "
                           + localDate + ": "
                           + lastDayOfYear);
    }
}
```

**Output:**

```java
last day of the year for localdate 2023-10-11: 2023-12-31

```

**程序 2:**

```java
// Java program to demonstrate
// TemporalAdjusters.lastDayOfYear() method

import java.time.LocalDate;
import java.time.temporal.TemporalAdjuster;
import java.time.temporal.TemporalAdjusters;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with last day
        // of  year adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.lastDayOfYear();

        // using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2099, 12, 29);
        LocalDate lastDayOfYear
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("last day of  "
                           + "year for localdate "
                           + localDate + ": "
                           + lastDayOfYear);
    }
}
```

**Output:**

```java
last day of  year for localdate 2099-12-29: 2099-12-31

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/temporalaadjusters . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/TemporalAdjusters.html)