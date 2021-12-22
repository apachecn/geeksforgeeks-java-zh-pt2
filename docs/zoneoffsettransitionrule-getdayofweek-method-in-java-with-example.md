# Java 中的 ZoneOffsetTransitionRule getDayOfWeek()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-getdayofweek-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-getdayofweek-method-in-java-with-example/)

类的 **getDayOfWeek()** 方法用于获取将要发生转换的 DayOfWeek 类型的枚举值。

**语法:**

```
public DayOfWeek getDayOfWeek()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回将要发生转换的 DayOfWeek 类型的枚举值。

以下是说明 **getDayOfWeek()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getDayOfWeek() method

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

        // getting Day Of Week
        // by using getDayOfWeek() method
        DayOfWeek day
            = zonetrans1.getDayOfWeek();

        // display the result
        System.out.println("Day Of Week : " + day);
    }
}
```

**输出:**

```
Day Of Week : SUNDAY

```

**例 2:**

```
// Java program to demonstrate
// getDayOfWeek() method

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
                      DayOfWeek.MONDAY,
                      LocalTime.of(03, 24, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition
                          .STANDARD,
                      ZoneOffset.ofTotalSeconds(8),
                      ZoneOffset.ofTotalSeconds(10),
                      ZoneOffset.ofTotalSeconds(12));

        // getting Day Of Week
        // by using getDayOfWeek() method
        DayOfWeek day = zonetrans1.getDayOfWeek();

        // display the result
        System.out.println("Day Of Week : " + day);
    }
}
```

**输出:**

```
Day Of Week : MONDAY

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransitionrule . html # getDayOfWeek–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#getDayOfWeek--)