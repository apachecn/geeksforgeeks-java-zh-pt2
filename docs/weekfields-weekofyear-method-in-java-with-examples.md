# Java 中 WeekFields weekOfYear()方法，带示例

> 原文:[https://www . geesforgeks . org/weekfields-week of year-in-Java-method-with-examples/](https://www.geeksforgeeks.org/weekfields-weekofyear-method-in-java-with-examples/)

**WeekFields 类**的 **weekOfYear()** 方法用于返回一个字段，根据该 WeekFields 访问一年中的某一周。
例:

*   如果一年中的第一天是星期一，那么第一周从第一天开始，没有零周
*   如果一年中的第二天是星期一，第一周从第二天开始，第一天是第零周
*   如果一年中的第四天是星期一，那么第一周从第四天开始，第一到第三天是第零周
*   如果一年中的第五天是星期一，那么第二周从 5 日开始，第一到第四周是第一周

此字段可用于任何日历系统。

**语法:**

```
public TemporalField weekOfYear()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个提供一年中某周访问权限的字段，不为空。

下面的程序说明了 WeekFields.weekOfYear()方法:
**程序 1:**

```
// Java program to demonstrate
// WeekFields.weekOfYear() method

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

        // apply weekOfYear()
        TemporalField weekOfYear
            = weekFields.weekOfYear();

        // create a LocalDate
        LocalDate day
            = LocalDate.of(2021, 12, 21);

        // get week of year for localdate
        int wow = day.get(weekOfYear);

        // print results
        System.out.println("Week of year for "
                           + day + " :" + wow);
    }
}
```

**Output:**

```
Week of year for 2021-12-21 :52

```

**程序 2:**

```
// Java program to demonstrate
// WeekFields.weekOfYear() method

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

        // apply weekOfYear()
        TemporalField weekOfYear
            = weekFields.weekOfYear();

        // create a LocalDate
        LocalDate day = LocalDate.of(2014, 10, 12);

        // get week of year for localdate
        int wow = day.get(weekOfYear);

        // print results
        System.out.println("Week of year for "
                           + day + " :" + wow);
    }
}
```

**Output:**

```
Week of year for 2014-10-12 :42

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # weekOfYear()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#weekOfYear())