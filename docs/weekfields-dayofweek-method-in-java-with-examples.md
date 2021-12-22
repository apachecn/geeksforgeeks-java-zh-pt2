# Java 中的 WeekFields dayOfWeek()方法，带示例

> 原文:[https://www . geesforgeks . org/weekfield-dayofweek-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weekfields-dayofweek-method-in-java-with-examples/)

**周字段类**的 **dayOfWeek()** 方法用于返回一个字段，根据该周字段访问一周中的某一天。例如，如果一周的第一天是星期一，那么它的值将为 1，而其他日期的范围从星期二为 2 到星期日为 7。

**语法:**

```java
public TemporalField dayOfWeek()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个字段，该字段提供对具有本地化编号的星期几的访问，而不是空值。

以下程序说明了 WeekFields.dayOfWeek()方法:
**程序 1:**

```java
// Java program to demonstrate
// WeekFields.dayOfWeek() method

import java.time.DayOfWeek;
import java.time.LocalDate;
import java.time.temporal.TemporalField;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);

        // apply dayOfWeek()
        TemporalField dayOfWeek
            = weekFields.dayOfWeek();

        // create a LocalDate
        LocalDate day = LocalDate.of(2021, 12, 21);

        // get day of week for localdate
        int dow = day.get(dayOfWeek);

        // print results
        System.out.println("day of week for "
                           + day + " :" + dow);
    }
}
```

**Output:**

```java
day of week for 2021-12-21 :2

```

**程序 2:**

```java
// Java program to demonstrate
// WeekFields.dayOfWeek() method

import java.time.DayOfWeek;
import java.time.LocalDate;
import java.time.temporal.TemporalField;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.SUNDAY, 1);

        // apply dayOfWeek()
        TemporalField dayOfWeek
            = weekFields.dayOfWeek();

        // create a LocalDate
        LocalDate day
            = LocalDate.of(2018, 05, 31);

        // get day of week for localdate
        int dow = day.get(dayOfWeek);

        // print results
        System.out.println("day of week for "
                           + day + " :" + dow);
    }
}
```

**Output:**

```java
day of week for 2018-05-31 :5

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # dayOfWeek()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#dayOfWeek())