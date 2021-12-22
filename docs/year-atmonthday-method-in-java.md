# Java 中的 Year atMonthDay()方法

> 原文:[https://www . geesforgeks . org/year-at month-day-in-method-in-Java/](https://www.geeksforgeeks.org/year-atmonthday-method-in-java/)

Java 中 year 类的 atMonthDay(MonthDay)方法将当前的 Year 对象与作为参数传递给它的 month-day 对象组合起来，创建一个 LocalDate 对象。

**语法**:

```
public LocalDate atMonthDay(MonthDay monthDay)

```

**参数**:此方法接受单个参数*月日*。它是 MonthDay 对象，指定要使用的月-日。它采用有效的月日对象，不能为空。

**返回值**:返回当前年份对象形成的 LocalDate 对象和作为参数传递给函数的有效 MonthDate 对象。

**注意**:如果当前年份不是闰年，作为参数传递的 MonthDay 对象指定“2 月 29 日”，则在生成的 LocalDate 对象中自动四舍五入为“2 月 28 日”。

下面的程序用 Java 说明了一年中的第几天(月日)方法:
**程序 1** :

```
// Program to illustrate the atMonthDay(MonthDay) method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year thisYear = Year.of(2017);

        // Creates a MonthDay object
        MonthDay monthDay = MonthDay.of(9, 15);

        // Creates a LocalDate with this
        // Year object and MonthDay passed to it
        LocalDate date = thisYear.atMonthDay(monthDay);

        System.out.println(date);
    }
}
```

**Output:**

```
2017-09-15

```

**程序二**:由于 2018 年不是闰年，下面的程序将 29 日四舍五入为 28 日。

```
// Program to illustrate the atMonthDay(MonthDay) method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year thisYear = Year.of(2018);

        // Creates a MonthDay object
        MonthDay monthDay = MonthDay.of(2, 29);

        // Creates a LocalDate with this
        // Year object and MonthDay passed to it
        LocalDate date = thisYear.atMonthDay(monthDay);

        System.out.println(date);
    }
}
```

**Output:**

```
2018-02-28

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # atmonth day-Java . time . monthday-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#atMonthDay-java.time.MonthDay-)