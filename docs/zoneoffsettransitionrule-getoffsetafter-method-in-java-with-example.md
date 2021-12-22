# Java 中的 ZoneOffsetTransitionRule getOffsetAfter()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-getoffsetafter-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-getoffsetafter-method-in-java-with-example/)

类的 **getOffsetAfter()** 方法用于获取过渡停止的特定时刻的区域偏移对象。

**语法:**

```
public ZoneOffset getOffsetAfter()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回在过渡停止的特定瞬间的区域偏移对象。

以下是举例说明 **getOffsetAfter()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getOffsetAfter() method

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

        // getting object of Zone offset
        // by using getOffsetAfter() method
        ZoneOffset off
            = zonetrans1.getOffsetAfter();

        // display the result
        System.out.println(
            "Zone Offset : " + off);
    }
}
```

**输出:**

```
Zone Offset : +00:00:12

```

**例 2:**

```
// Java program to demonstrate
// getOffsetAfter() method

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
                      ZoneOffset.ofTotalSeconds(18),
                      ZoneOffset.ofTotalSeconds(17));

        // getting object of Zone offset
        // by using getOffsetAfter() method
        ZoneOffset off
            = zonetrans1.getOffsetAfter();

        // display the result
        System.out.println("Zone Offset : " + off);
    }
}
```

**输出:**

```
Zone Offset : +00:00:17

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition rule . html # getoffset after--](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#getOffsetAfter--)