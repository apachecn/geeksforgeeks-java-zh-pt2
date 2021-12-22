# Java 中的 WeekFields weekOfWeekBasedYear()方法，示例

> 原文:[https://www . geesforgeks . org/weekfields-weekofweekbasedier-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weekfields-weekofweekbasedyear-method-in-java-with-examples/)

**WeekFields 类**的**weekofweekbase dyer()**方法用于返回一个字段，以访问基于该 WeekFields 的一年中的一周。
例:

*   如果一年中的第一天是星期一，那么第一周从第一天开始
*   如果一年的第二天是星期一，那么第一周从第二天开始，第一周是上一年的最后一周
*   如果一年中的第四天是星期一，那么第一周从第四天开始，第一天到第三天是上一年的最后一周
*   如果一年中的第五天是星期一，那么第二周从 5 日开始，第一到第四周是第一周

此字段可用于任何日历系统。

**语法:**

```
public TemporalField weekOfWeekBasedYear()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回一个字段，该字段提供对基于周的年的访问，而不是空值。

下面的程序说明了 WeekFields.weekOfWeekBasedYear()方法:
**程序 1:**

```
// Java program to demonstrate
// WeekFields.weekOfWeekBasedYear() method

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

        // apply weekOfWeekBasedYear()
        TemporalField weekOfWeekBasedYear
            = weekFields.weekOfWeekBasedYear();

        // create a LocalDate
        LocalDate day = LocalDate.of(2021, 12, 21);

        // get week of week for localdate
        int wow = day.get(weekOfWeekBasedYear);

        // print results
        System.out.println("Week of week for "
                           + day + " :" + wow);
    }
}
```

**Output:**

```
Week of week for 2021-12-21 :52

```

**程序 2:**

```
// Java program to demonstrate
// WeekFields.weekOfWeekBasedYear() method

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

        // apply weekOfWeekBasedYear()
        TemporalField weekOfWeekBasedYear
            = weekFields.weekOfWeekBasedYear();

        // create a LocalDate
        LocalDate day = LocalDate.of(2014, 10, 12);

        // get week of week for localdate
        int wow = day.get(weekOfWeekBasedYear);

        // print results
        System.out.println("Week of week for "
                           + day + " :" + wow);
    }
}
```

**Output:**

```
Week of week for 2014-10-12 :42

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # weekofweekbasedier()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#weekOfWeekBasedYear())