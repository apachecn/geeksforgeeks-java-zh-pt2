# Java 中的 ZoneOffsetTransitionRule getOffsetBefore()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-getoffsetbefore-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-getoffsetbefore-method-in-java-with-example/)

类的 **getOffsetBefore()** 方法用于获取过渡开始的特定时刻的区域偏移对象。

**语法:**

```
public ZoneOffset getOffsetBefore()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回在过渡开始的特定时刻的区域偏移对象。

下面是举例说明 **getOffsetBefore()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getOffsetBefore() method

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
        // by using getOffsetBefore() method
        ZoneOffset off
            = zonetrans1.getOffsetBefore();

        // display the result
        System.out.println(
            "Zone Offset before : " + off);
    }
}
```

**输出:**

```
Zone Offset before : +00:00:10

```

**例 2:**

```
// Java program to demonstrate
// getOffsetBefore() method

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

        // getting object of Zone offset
        // by using getOffsetBefore() method
        ZoneOffset off
            = zonetrans1.getOffsetBefore();

        // display the result
        System.out.println(
            "Zone Offset before : " + off);
    }
}
```

**输出:**

```
Zone Offset before : +00:00:17

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition rule . html # getffset before】](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#getOffsetBefore--)