# Java 中的临时调整器 previousOrSame()方法，示例

> 原文:[https://www . geesforgeks . org/temporalaadjusters-previousor name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/temporaladjusters-previousorsame-method-in-java-with-examples/)

**时间调整类**的**previousOrSame(DayOfWeek)**方法用于返回一个前一个或同一天的时间调整对象，该对象可用于从应用此时间调整的任何日期对象中获取一个新的日期对象，该日期对象是前一个或同一个匹配的星期几作为参数传递的日期对象。

**语法:**

```
public static TemporalAdjuster
       previousOrSame(DayOfWeek dayOfWeek)

```

**参数:**该方法接受 **dayOfWeek** ，可用于获取一个新的日期对象，该对象是上一个或同一个日期，匹配的星期几相同。它不应为空。

**返回值:**该方法返回一个前一个或同一天的临时调整对象。

下面的程序说明了临时调整程序.前一个程序名()方法:
**程序 1:**

```
// Java program to demonstrate
// TemporalAdjusters.previousOrSame()

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get TemporalAdjuster with the
        // previousOrSame() of month adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters
                  .previousOrSame(
                      DayOfWeek.FRIDAY);

        // Using adjuster for local date-time
        LocalDate localDate
            = LocalDate.of(2020, 10, 30);
        LocalDate previousOrSameDOW
            = localDate.with(temporalAdjuster);

        // Print
        System.out.println(
            "Previous or same date "
            + "having FRIDAY for localdate "
            + localDate + " is: "
            + previousOrSameDOW);
    }
}
```

**Output:**

```
Previous or same date having FRIDAY for localdate 2020-10-30 is: 2020-10-30

```

**程序 2:**

```
// Java program to demonstrate
// TemporalAdjusters previousOrSame() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get TemporalAdjuster with the
        // previousOrSame() day of week adjuster
        TemporalAdjuster temporalAdjuster
            = TemporalAdjusters
                  .previousOrSame(
                      DayOfWeek.THURSDAY);

        // Using adjuster for local date time
        LocalDate localDate
            = LocalDate.of(2018, 02, 23);
        LocalDate previousOrSameDOW
            = localDate.with(temporalAdjuster);

        // Print
        System.out.println(
            "Previous or same date "
            + "having THURSDAY for localdate "
            + localDate + " is: "
            + previousOrSameDOW);
    }
}
```

**Output:**

```
Previous or same date having THURSDAY for localdate 2018-02-23 is: 2018-02-22

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporalaadjusters . html # previousOrSame(Java . time . dayofweek)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/TemporalAdjusters.html#previousOrSame(java.time.DayOfWeek))