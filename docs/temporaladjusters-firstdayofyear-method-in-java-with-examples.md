# Java 中的 temporalaadjusters first dayofyear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/temporaladjasters-first dayofyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-firstdayofyear-method-in-java-with-examples/)

**时间调整类**的**first dayofyeear()**方法用于返回“一年的第一天”时间调整对象，该对象返回设置为一年的第一天的新的 Date 对象。

**语法:**

```java
public static TemporalAdjuster firstDayOfYear()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回年度调整器的第一天，不为空。

下面的程序说明了临时调整的第一天()方法:
**程序 1:**

```java
// Java program to demonstrate
// TemporalAdjusters.firstDayOfYear()

import java.time.LocalDate;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with first day
        // of the year adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.firstDayOfYear();

        // using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2012, 05, 31);
        LocalDate firstDayOfYear
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("First day of the "
                           + "year for localdate "
                           + localDate + ": "
                           + firstDayOfYear);
    }
}
```

**Output:**

```java
First day of the year for localdate 2012-05-31: 2012-01-01

```

**程序 2:**

```java
// Java program to demonstrate
// TemporalAdjusters.firstDayOfYear() method

import java.time.LocalDate;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get TemporalAdjuster with first day
        // of the year adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters.firstDayOfYear();

        // using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2000, 12, 21);
        LocalDate firstDayOfYear
            = localDate.with(temporalAdjuster);

        // print
        System.out.println("First day of the "
                           + "year for localdate "
                           + localDate + ": "
                           + firstDayOfYear);
    }
}
```

**Output:**

```java
First day of the year for localdate 2000-12-21: 2000-01-01

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/temporalaadjusters . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/TemporalAdjusters.html)