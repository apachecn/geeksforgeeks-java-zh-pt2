# Java 中 weekfield getminimaldaysinfirst week()方法，带示例

> 原文:[https://www . geesforgeks . org/weekfields-getminimaldaysinfirst week-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weekfields-getminimaldaysinfirstweek-method-in-java-with-examples/)

**WeekFields 类**的**getminimaldaysinfirst week()**方法用于返回一个月或一年的第一周的最小天数。例如，ISO-8601 要求在计算第一周之前有 4 天(超过半周)的时间。此方法返回一个月或一年中第一周的最小天数，从 1 到 7。

**语法:**

```
public int getMinimalDaysInFirstWeek()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回一个月或一年的第一周的最小天数，从 1 到 7。

下面的程序说明了 weekfields . getminimaldaysinfirst week()方法:
**程序 1:**

```
// Java program to demonstrate
// WeekFields.getMinimalDaysInFirstWeek() method

import java.time.DayOfWeek;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.SATURDAY, 2);

        // apply getMinimalDaysInFirstWeek()
        int noOfDays
            = weekFields.getMinimalDaysInFirstWeek();

        // print results
        System.out.println("Minimal number of days"
                           + " in the first week: "
                           + noOfDays);
    }
}
```

**Output:**

```
Minimal number of days in the first week: 2

```

**程序 2:**

```
// Java program to demonstrate
// WeekFields.getMinimalDaysInFirstWeek() method

import java.time.temporal.WeekFields;
import java.util.Locale;

public class GFG {
    public static void main(String[] args)
    {

        Locale locale = new Locale("EN", "INDIA");

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(locale);

        // apply getMinimalDaysInFirstWeek()
        int noOfDays
            = weekFields.getMinimalDaysInFirstWeek();

        // print results
        System.out.println("Minimal number of days"
                           + " in the first week: "
                           + noOfDays);
    }
}
```

**Output:**

```
Minimal number of days in the first week: 1

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # getminimaldaysinfirst week()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#getMinimalDaysInFirstWeek())