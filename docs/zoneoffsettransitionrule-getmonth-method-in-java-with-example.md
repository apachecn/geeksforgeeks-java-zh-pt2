# Java 中的 ZoneOffsetTransitionRule getMonth()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-get month-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-getmonth-method-in-java-with-example/)

类的 **getMonth()** 方法用于获取发生转换的月份的对象。

**语法:**

```
public Month getMonth()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回将要发生转换的月份对象。

以下是说明 **getMonth()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getMonth() method

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

        // getting object of months
        // by using getMonth() method
        Month mon = zonetrans1.getMonth();

        // display the result
        System.out.println("Month : " + mon);
    }
}
```

**输出:**

```
Month : JANUARY

```

**例 2:**

```
// Java program to demonstrate
// getMonth() method

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
                      Month.MARCH, 12,
                      DayOfWeek.SUNDAY,
                      LocalTime.of(03, 24, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition
                          .STANDARD,
                      ZoneOffset.ofTotalSeconds(8),
                      ZoneOffset.ofTotalSeconds(10),
                      ZoneOffset.ofTotalSeconds(12));

        // getting object of months
        // by using getMonth() method
        Month mon = zonetrans1.getMonth();

        // display the result
        System.out.println("Month : " + mon);
    }
}
```

**输出:**

```
Month : MARCH

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition rule . html # getmonth】](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#getMonth--)