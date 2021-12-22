# Java 中的 ZoneOffsetTransitionRule createTransition()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-create transition-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-createtransition-method-in-java-with-example/)

**Java . time . zoneoffset transitionrule**类的 **createTransition()** 方法用于
创建特定年份的特定区域偏移转换的对象。

**语法:**

```java
public ZoneOffsetTransition createTransition(int year)
```

**参数:**该方法取必须生成过渡实例的整数值年份..

**返回值:**该方法返回特定年份特定区域偏移过渡的对象。

以下是说明 **createTransition()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// createTransition() method

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

        // getting object of ZoneOffsetTransition
        // by using createTransition() method
        ZoneOffsetTransition zoo
            = zonetrans1.createTransition(10);

        // display the result
        System.out.println("ZoneOffsetTransition : "
                           + zoo);
    }
}
```

**Output:**

> 区域偏移转换:转换[0010-01-17T 03:24:47+00:00:10 到+00:00:12 的间隙]

**例 2:**

```java
// Java program to demonstrate
// createTransition() method

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

        // getting object of ZoneOffsetTransition
        // by using createTransition() method
        ZoneOffsetTransition zoo
            = zonetrans1.createTransition(14);

        // display the result
        System.out.println(
            "ZoneOffsetTransition : "
            + zoo);
    }
}
```

**Output:**

> 区域偏移转换:转换[0014-01-12t 03:24:47+00:00:10 到+00:00:12 的间隙]

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition rule . html # create transition-int-](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#createTransition-int-)