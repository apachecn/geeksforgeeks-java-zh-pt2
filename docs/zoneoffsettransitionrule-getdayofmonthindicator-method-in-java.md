# Java 中的 ZoneOffsetTransitionRule getdayofmonth indicator()方法

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-getdayofmonth indicator-method-in-Java/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-getdayofmonthindicator-method-in-java/)

Java . time . zone . zoneoffsettransitionrule 类的 **getDayOfMonthIndicator()** 方法用于获取该转换实际发生的日期。

**语法:**

```java
public int getDayOfMonthIndicator()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回实际发生转换的日期。

以下是举例说明**getdayofmonthsindicator()**方法的例子:

**例 1:**

```java
// Java program to demonstrate
// getDayOfMonthIndicator() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;

public class GFG {
    public static void main(String[] argv)
    {

        // creating and initializing
        // ZoneOffsetTransitionRule Object
        ZoneOffsetTransitionRule zonetrans1
            = ZoneOffsetTransitionRule
                  .of(
                      Month.JANUARY, 12,
                      DayOfWeek.SUNDAY,
                      LocalTime.of(03, 24, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition
                          .STANDARD,
                      ZoneOffset.ofTotalSeconds(8),
                      ZoneOffset.ofTotalSeconds(10),
                      ZoneOffset.ofTotalSeconds(12));

        // getting Day Of Month Indicator
        // by using getDayOfMonthIndicator() method
        int day
            = zonetrans1.getDayOfMonthIndicator();

        // display the result
        System.out.println(
            "Day Of Month Indicator : " + day);
    }
}
```

**输出:**

```java
Day Of Month Indicator : 12

```

**例 2:**

```java
// Java program to demonstrate
// getDayOfMonthIndicator() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;

public class GFG {
    public static void main(String[] argv)
    {

        // creating and initializing
        // ZoneOffsetTransitionRule Object
        ZoneOffsetTransitionRule zonetrans1
            = ZoneOffsetTransitionRule
                  .of(
                      Month.JANUARY, 20,
                      DayOfWeek.SUNDAY,
                      LocalTime.of(03, 24, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition
                          .STANDARD,
                      ZoneOffset.ofTotalSeconds(8),
                      ZoneOffset.ofTotalSeconds(10),
                      ZoneOffset.ofTotalSeconds(12));

        // getting Day Of Month Indicator
        // by using getDayOfMonthIndicator() method
        int day
            = zonetrans1.getDayOfMonthIndicator();

        // display the result
        System.out.println(
            "Day Of Month Indicator : " + day);
    }
}
```

**输出:**

```java
Day Of Month Indicator : 20

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransitionrule . html # getdayofmonth indicator–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#getDayOfMonthIndicator--)