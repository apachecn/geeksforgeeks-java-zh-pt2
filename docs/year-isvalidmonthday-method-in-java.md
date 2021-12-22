# Year 是 Java 中的 ValidMonthDay()方法

> 原文:[https://www . geesforgeks . org/year-isvalidmonthday-method-in-Java/](https://www.geeksforgeeks.org/year-isvalidmonthday-method-in-java/)

Java 中 Year 类的 isValidMonthDay()方法用于检查 Year 对象和作为该方法的参数提供的 MonthDay 所表示的月-日是否可以一起构成有效日期。

**语法**:

```
public boolean isValidMonthDay(MonthDay monthDay)

```

**参数**:该方法接受单个参数*月日*，表示需要用本年度对象检查的月日。

**返回值**:如果这个 Year 对象和一个 MonthDay 表示的给定的月-日可以一起组成一个有效的日期，则返回布尔值 True，否则返回 False。

以下程序说明了 Java 中的 isValidMonthDay()年方法:
**程序 1** :

```
// Program to illustrate the isValidMonthDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a Year object
        Year thisYear = Year.of(2016);

        // Creates a MonthDay object
        MonthDay monthDay = MonthDay.of(9, 15);

        // Check if this year object and given
        // MonthDay forms a valid date
        System.out.println(thisYear.isValidMonthDay(monthDay));
    }
}
```

**Output:**

```
true

```

**程序 2** :在下面的程序中，Year 是指 1990 年，它不是闰年，而是月日代表闰年。因此，它们不能一起形成有效的日期，因此该方法将返回 false。

```
// Program to illustrate the isValidMonthDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create a Year object
        Year thisYear = Year.of(1990);

        // Creates a MonthDay object
        MonthDay monthDay = MonthDay.of(2, 29);

        // Check if this year object and given
        // MonthDay forms a valid date
        System.out.println(thisYear.isValidMonthDay(monthDay));
    }
}
```

**Output:**

```
false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # isValidMonthDay-Java . time . monthday-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#isValidMonthDay-java.time.MonthDay-)