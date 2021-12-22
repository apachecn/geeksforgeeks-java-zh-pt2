# Java 中的 WeekFields weekBasedYear()方法，带示例

> 原文:[https://www . geesforgeks . org/weekfields-weekbase dyer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/weekfields-weekbasedyear-method-in-java-with-examples/)

**WeekFields 类**的**weekbasedayer()**方法用于返回一个字段，以基于该 WeekFields 访问一年中的某一周。此字段可用于任何日历系统。

**语法:**

```
public TemporalField weekBasedYear()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个可以访问以周为单位的年份的字段，不为空。

下面的程序说明了 WeekFields.weekBasedYear()方法:
**程序 1:**

```
// Java program to demonstrate
// WeekFields.weekBasedYear() method

import java.time.DayOfWeek;
import java.time.temporal.TemporalField;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.MONDAY, 1);

        // apply weekBasedYear()
        TemporalField weekBasedYear
            = weekFields.weekBasedYear();

        // print results
        System.out.println(weekBasedYear);
    }
}
```

**Output:**

```
WeekBasedYear[WeekFields[MONDAY, 1]]

```

**程序 2:**

```
// Java program to demonstrate
// WeekFields.weekBasedYear() method

import java.time.DayOfWeek;
import java.time.temporal.TemporalField;
import java.time.temporal.WeekFields;

public class GFG {
    public static void main(String[] args)
    {

        // create WeekFields
        WeekFields weekFields
            = WeekFields.of(DayOfWeek.SUNDAY, 1);

        // apply weekBasedYear()
        TemporalField weekBasedYear
            = weekFields.weekBasedYear();

        // print results
        System.out.println(weekBasedYear);
    }
}
```

**Output:**

```
WeekBasedYear[WeekFields[SUNDAY, 1]]

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/weekfields . html # weekbasedayer()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/WeekFields.html#weekBasedYear())