# Java 中的 zoneoffset transitionrule getstandardoft()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-getstandard offset-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-getstandardoffset-method-in-java-with-example/)

**Java . time . zoneoffset transitionrule**类的 **getStandardOffset()** 方法用于获取发生转换的标准区域偏移的对象。

**语法:**

```
public ZoneOffset getStandardOffset()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回发生转换的标准区域偏移的对象。

下面是举例说明**getstandardpoffset()**方法的例子:

**例 1:**

```
// Java program to demonstrate
// getStandardOffset() method

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
        // by using getStandardOffset() method
        ZoneOffset off
            = zonetrans1.getStandardOffset();

        // display the result
        System.out.println(
            "standard Zone Offset : " + off);
    }
}
```

**输出:**

```
standard Zone Offset : +00:00:08

```

**例 2:**

```
// Java program to demonstrate
// getStandardOffset() method

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
                      ZoneOffset.ofTotalSeconds(21),
                      ZoneOffset.ofTotalSeconds(17),
                      ZoneOffset.ofTotalSeconds(12));

        // getting object of Zone offset
        // by using getStandardOffset() method
        ZoneOffset off
            = zonetrans1.getStandardOffset();

        // display the result
        System.out.println(
            "standard Zone Offset : " + off);
    }
}
```

**输出:**

```
standard Zone Offset : +00:00:21

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition rule . html # getsstandardoffset】](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#getStandardOffset--)