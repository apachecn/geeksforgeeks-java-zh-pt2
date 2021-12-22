# Java 中 WeekFields getFirstDayOfWeek()方法示例

> 原文:[https://www . geesforgeks . org/weekfields-getfirst dayofweek-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weekfields-getfirstdayofweek-method-in-java-with-examples/)

**WeekFields 类**的**getfirst DayOfWeek()**方法用于将一周的第一天作为 day week 枚举返回。比如美国用周日，法国用周一。

**语法:**

```
public DayOfWeek getFirstDayOfWeek()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回一周的第一天，不为空。

下面的程序说明了 WeekFields.getFirstDayOfWeek()方法:
**程序 1:**

```
// Java program to demonstrate
// WeekFields.getFirstDayOfWeek() method

import java.time.DayOfWeek;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);

        // apply getFirstDayOfWeek()
        DayOfWeek firstDay
            = weekFields.getFirstDayOfWeek();

        // print results
        System.out.println("First Day:"
                           + firstDay);
    }
}
```

**Output:**

```
First Day:MONDAY

```

**程序 2:**

```
// Java program to demonstrate
// WeekFields.getFirstDayOfWeek() method

import java.time.DayOfWeek;
import java.time.temporal.WeekFields;
import java.util.Locale;

public class GFG {
    public static void main(String[] args)
    {

        Locale locale = new Locale("EN", "US");

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(locale);

        // apply getFirstDayOfWeek()
        DayOfWeek firstDay
            = weekFields.getFirstDayOfWeek();

        // print results
        System.out.println("First Day:"
                           + firstDay);
    }
}
```

**Output:**

```
First Day:SUNDAY

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # getfirst dayofweek()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#getFirstDayOfWeek())