# 周字段周月()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/weekfields-weekofmonth-in-Java-method-with-examples/](https://www.geeksforgeeks.org/weekfields-weekofmonth-method-in-java-with-examples/)

**weekfield 类**的 **weekOfMonth()** 方法是基于这个 weekfield 返回字段访问一个月中的星期。
例如:

*   如果一个月的第一天是星期一，那么第一周从第一天开始，没有零周
*   如果一个月的第二天是星期一，第一周从第二天开始，第一天是第零周
*   如果一个月的第四天是星期一，第一周从第四天开始，第一天到第三天是第零周
*   如果一个月的第五天是星期一，那么第二周从 5 日开始，第一至第四周是第一周

此字段可用于任何日历系统。

**语法:**

```java
public TemporalField weekOfMonth()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个可以访问以周为单位的年份的字段，不为空。

下面的程序说明了 WeekFields.weekOfMonth()方法:
**程序 1:**

```java
// Java program to demonstrate
// WeekFields.weekOfMonth() method

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

        // apply weekOfMonth()
        TemporalField weekOfMonth
            = weekFields.weekOfMonth();

        // create a LocalDate
        LocalDate day
            = LocalDate.of(2021, 12, 21);

        // get week of month for localdate
        int wom = day.get(weekOfMonth);

        // print results
        System.out.println("week of month for "
                           + day + " :" + wom);
    }
}
```

**Output:**

```java
week of month for 2021-12-21 :4

```

**程序 2:**

```java
// Java program to demonstrate
// WeekFields.weekOfMonth() method

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

        // apply weekOfMonth()
        TemporalField weekOfMonth
            = weekFields.weekOfMonth();

        // create a LocalDate
        LocalDate day = LocalDate.of(2020, 01, 10);

        // get week of month for localDate
        int wom = day.get(weekOfMonth);

        // print results
        System.out.println("week of month for "
                           + day + " :" + wom);
    }
}
```

**Output:**

```java
week of month for 2020-01-10 :2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # weekOfMonth()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#weekOfMonth())