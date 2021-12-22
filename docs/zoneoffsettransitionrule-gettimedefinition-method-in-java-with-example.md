# Java 中的 ZoneOffsetTransitionRule getTimeDefinition()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-gettimedefinition-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-gettimedefinition-method-in-java-with-example/)

**Java . time . zone . ZoneOffsetTransitionRule**类的 **getTimeDefinition()** 方法用于获取 ZoneOffsetTransitionRule 的枚举值。发生转换的时间定义对象。

**语法:**

```
public ZoneOffsetTransitionRule.TimeDefinition getTimeDefinition()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回 ZoneOffsetTransitionRule 的枚举值。发生转换的时间定义对象。

以下是说明 **getTimeDefinition()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getTimeDefinition() method

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
                      ZoneOffset.ofTotalSeconds(17),
                      ZoneOffset.ofTotalSeconds(12));

        // getting value of TimeDefinition
        // by using getTimeDefinition() method
        ZoneOffsetTransitionRule.TimeDefinition
            time
            = zonetrans1.getTimeDefinition();

        // display the result
        System.out.println(
            "TimeDefinition : " + time);
    }
}
```

**输出:**

```
TimeDefinition : STANDARD

```

**例 2:**

```
// Java program to demonstrate
// getTimeDefinition() method

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
                      Month.JANUARY,
                      12,
                      DayOfWeek.SUNDAY,
                      LocalTime.of(03, 24, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition.UTC,
                      ZoneOffset.ofTotalSeconds(8),
                      ZoneOffset.ofTotalSeconds(17),
                      ZoneOffset.ofTotalSeconds(12));

        // getting value of TimeDefinition
        // by using getTimeDefinition() method
        ZoneOffsetTransitionRule.TimeDefinition
            time
            = zonetrans1.getTimeDefinition();

        // display the result
        System.out.println(
            "TimeDefinition : " + time);
    }
}
```

**输出:**

```
TimeDefinition : UTC

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition rule . html # gettime definition】](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#getTimeDefinition--)